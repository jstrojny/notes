Dimensions are ways to group or filter data based on conditions and are used by the dbt [[Semantic Models|semantic layer]]. They allow us to add extra data about models that would be difficult to model directly.

A dimension is comprised of three parts: a name, a type, with a description and expr as optional parts. The name of a dimension is a unique to the semantic model identifier, the type defines what kind of dimension it is: time, categorial, or slow changing. The expr value can be either a column name or sql statement such as a `case when`.