First normal form is the base [[Normalization|normalization]] and is achieved by removing grouped data within a table. For example a table of students and their personal information where a student can have multiple phone numbers. If those phone numbers are all part of a single row the table is not in first normal form. 

To put it in first normal form each row with grouped data should be split into multiple rows.

### Not Normalized
| ID | Name | Phone | Street Addr |
|----|------|-------|-------------|
| 1 | Jake | 555-555-5555,666-666-6666| 555 School St. |

### Normalized
| ID | Name | Phone      | Street Addr    |
|----|------|------------|----------------|
| 1 | Jake | 555-555-5555| 555 School St. |
| 1 | Jake | 666-666-6666| 555 School St. |
