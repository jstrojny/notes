A technique used to breakup data into dimensions and facts that describe entities within a data warehouse.

## Fact
A fact is a collection of information that refers to a specific entity: an event such as account creation, person, or business result such as monthly revenue. Facts are almost never written as their historical context can provide additional insights. Facts can often be thought of as verbs, they are things that have happened.

## Dimensions
Dimensions are closer to nouns as opposed to verbs. They describe discrete entities: who took an action, what system was affected. When a change happens to that entity the row is updated as opposed to a fact where a new row would be appended. These dimensions provide greater context to a list of facts without denormalizing the database entirely.

Deciding if something should be a fact or dimension really comes down to how the end users will consume the data. It should be modeled based on how the data team feels is appropriate. Remodeling a fact to a dimension or vice versa is relatively easy and data naturally evolves so picking one or the other should not be thought of as an irreversible action.