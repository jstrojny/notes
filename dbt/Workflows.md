dbt comes with a set of commands for building and testing our models. These commands also provide operators to build only subsets of commands.

## Commands
`--select`: this flag works for both build and run. It allows us to select a specific model, a directory, or a tag for what should be built. These can also be combined to more directly target what should be built such as all models in a directory that have a specific tag `--select="./path/to/directory,tag:specific_tag"`. In addition to intersections this command supports unions: `select="model_x model_y` would build both models.

## Intersections
Some commands support intersections. In the case of `--select` this is done by giving it a list of models/paths/etc separated by commas: `select="./path/to/directory,tag:specific_tag"`

## Unions
Some commands support intersections. In the case of `--select` this is done by giving it a list of models/paths/etc separated by spaces: `select="./path/to/directory tag:specific_tag"`

## Operators
The above commands also have special operators that can adjust the scope of the command. The `+` can be appended before or after a selector to build its ancestors or children respectively. This can be combined with Unions or Intersections to more heavily target what is built: `select="model_a+ model_b+"` would build all the descendants of model_a and model_b.