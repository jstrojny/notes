Semantic models lay the foundation for dbt's [[MetricFlow]] subsystem which powers the semantic layer. Each semantic model corresponds to one existing model, multiple semantic models can come from the same existing model as long as each semantic model's name is unique. These semantic models are created by providing a yml file. Semantic models can be configured at both the project level and the schema level. It is considered a best practice for semantic models to be defined in `models/semantic_models`.

Semantic models are comprised of three main groups of components: [[Entities|entities]], [[Dimensions||dimensions]], and [[Measures||measures]].

Semantic models have six components described by the below table.

| Component | Description | Required |
| ---- | ---- | ---- |
| Name | Unique name without double underscores | Yes |
| Description | Describes the semantic model | No |
| Model | dbt model to use referenced by `ref()` | Yes |
| Defaults | Default for the semantic model | Yes |
| Entities | Use the columns from entities as join keys. Can be marked as primary, foreign, or unique. | Yes |
| Primary Entity | If there is a primary entity this is optional, otherwise it is required | N/A |
| Dimenions | How to group or slice data for a metric. Can be time or categorical | Yes |
| Measures | Aggregations applied to columns. Can be the final value or just a building block. | No |
| Label | The display name. | No |


**Example semantic.yml:**
```yml semantic_model_example.yml
semantic_models:
  - name: transaction # A semantic model with the name Transactions
    model: ref('fact_transactions') # References the dbt model named `fact_transactions`
    description: "Transaction fact table at the transaction level. This table contains one row per transaction and includes the transaction timestamp."
    defaults:
      agg_time_dimension: transaction_date

    entities: # Entities included in the table are defined here. MetricFlow will use these columns as join keys.
      - name: transaction
        type: primary
        expr: transaction_id
      - name: customer
        type: foreign
        expr: customer_id

    dimensions: # dimensions are qualitative values such as names, dates, or geographical data. They provide context to metrics and allow "metric by group" data slicing.
      - name: transaction_date
        type: time
        type_params:
          time_granularity: day

      - name: transaction_location
        type: categorical
        expr: order_country

    measures: # Measures are columns we perform an aggregation over. Measures are inputs to metrics.
      - name: transaction_total
        description: "The total value of the transaction."
        agg: sum

      - name: sales
        description: "The total sale of the transaction."
        agg: sum
        expr: transaction_total

      - name: median_sales
        description: "The median sale of the transaction."
        agg: median
        expr: transaction_total

  - name: customers # Another semantic model called customers.
    model: ref('dim_customers')
    description: "A customer dimension table."

    entities:
      - name: customer
        type: primary
        expr: customer_id

    dimensions:
      - name: first_name
        type: categorical
```


## Sources
[dbt Semantic Models Documentation](https://docs.getdbt.com/docs/build/semantic-models)

