This is where our data is transformed by applying layers of logic. It is also where we begin combining the base models from Staging. The subdirectories here _should_ be broken down by business unit. Files names should also follow the format `int_[entity]s_[verb].sql`
to explain what sort of transformation is being applied to the building block.

These file names also serve a documentary purpose: telling a reader what is happening in this intermediate step. Where the total DAG shows the context of data through the whole system a single file with a good name shows the context within a smaller intermediate step.

These models are also not intended for view by end users, they merely provide the steps of transformation. To that end they do not necessarily need to be materialized into a view; an ephemeral view may be more efficient although likely more difficult to debug.

Ideally the DAG should be arrow shaped, as sources are added and intermediate steps performed our outputs should become narrow as our data is collated into use for business.