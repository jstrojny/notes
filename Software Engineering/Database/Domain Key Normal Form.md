A type of [[Normalization|normalization]] where the table has both a primary key constraint and domain constraints. A primary key constraint means at least one column must uniquely identify each entry in the table. A domain constraint means some of the data's value has a constraint defined by the domain.

For instance in a table of students, their grade, and a remark on that grade the student id would be the primary key and the value of the remark is a domain constraint because it is defined by the value of their marks.

To keep this data consistent it is best to split it into multiple tables. Students and their marks in one table while remarks with what marks are their minimum and maximum go in a second table.

## Not in DKNF
| ID | Name | Mark | Remark |
|----|------|------|--------|
| 1  | Jake | 90   | Good   |
| 2  | Alex | 100  | Amazing| 

The above table is not in DKNF because Good and Amazing are derived from Mark but the constraint is not clear.

| ID | Name | Mark |
|----|------|------|
| 1  | Jake | 90   |
| 2  | Alex | 100  |

| Remark | Min | Max |
|--------|-----|-----|
| Amazing| 90  | 100 |
| Good   | 80  | 89  |
| Okay   | 70  | 79  |
| Bad    | 60  | 69  |
| Fail   | 0   | 59  |

Now the table is in DKNF because the domain constraints are defined. Additionally, because the domain constraints are in their own table inserts and deletions can not cause a bad state. 