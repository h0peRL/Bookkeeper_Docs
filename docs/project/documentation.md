# Documentation

## Inform

### Sources

### Requirements


| **Req. No.** | **Mandatory/Optional** | **Func./Qual./Margin.** | **Requirement**                                                                                |
| :----------- | ---------------------- | :---------------------- | ---------------------------------------------------------------------------------------------- |
| 1            | Mandatory              | Functional              | The app supports multiple users at the same time                                               |
| 2            | Mandatory              | Marginal                | The app is a .NET 8.0 REST-API (LTS)                                                           |
| 3            | Mandatory              | Functional              | Data will be stored in an SQL-Database                                                         |
| 4            | Mandatory              | Functional              | The user can register via HTTP-request                                                         |
| 5            | Mandatory              | Functional              | The user can log in via HTTP-request                                                           |
| 6            | Mandatory              | Functional              | The user can create booking records via HTTP-request                                           |
| 7            | Mandatory              | Functional              | The software must have a balance sheet according to the SME chart of accounts                  |
| 8            | Optional               | Functional              | The software must have an income statement based on the SME chart of accounts                  |
| 9            | Mandatory              | Functional              | The software must be able to execute booking records while updating the affected accounts      |
| 10           | Mandatory              | Functional              | A booking record must include the date, booking text, debit account, credit account and amount |
| 11           | Optional               | Quality                 | Every command should have an explanation of the syntax                                         |
| 12           | Mandatory              | Functional              | Every endpoint should require a JWT-Bearer-Token (except login and register)                   |
| 13           | Mandatory              | Marginal                | There must be a UML class diagram.                                                             |
| 14           | Mandatory              | Marginal                | The program and documentation should be in english                                             |
| 15           | Mandatory              | Marginal                | There should be a glossary with german translations                                            |

### Technologies

## Plan

### Work Packages


| Nr. | Due Date   | Description                                                                      | Estimated Time (45 min.) |
| --- | ---------- | -------------------------------------------------------------------------------- | ------------------------ |
| 0   | 25.01.2024 | Create table with work packages                                                  | 2                        |
| 1   | 18.01.2024 | Set up documentation                                                             | 3                        |
| 2   | 18.01.2024 | Set up project                                                                   | 3                        |
| 3   | 18.01.2024 | Set up repositories                                                              | 2                        |
| 4   | 18.01.2024 | Define detailed requirements                                                     | 2                        |
| 5   | 01.02.2024 | Set up shared (prod.) DB (with users)                                            | 5                        |
| 6   | 25.01.2024 | Research Technologies                                                            | 5                        |
| 7   | 25.01.2024 | Create detailed MVC class diagram in VP                                          | 15                       |
| 8   | 25.01.2024 | Decide about technologies to use                                                 | 3                        |
| 9   | 25.01.2024 | Set up test DB (with users)                                                      | 5                        |
| 10  | 25.01.2024 | Set up linter and styling rules                                                  | 2                        |
| 11  | 01.02.2024 | Set up CI pipelines                                                              | 5                        |
| 12  | 01.02.2024 | Set up pre-commits                                                               | 1                        |
| 13  | 01.02.2024 | Write test cases for every requirement with test env. definition (documentation) | 5                        |
| 14  | 01.02.2024 | Write unittests from test cases (for model only!)                                | 6                        |
| 15  | 25.01.2024 | Integrate EF as ORM with DB                                                      | 5                        |
| 16  | 25.01.2024 | Create class and method bodies from class diagram                                | 2                        |
| 17  | 22.02.2024 | Implement registration endpoint                                                  | 2                        |
| 18  | 22.02.2024 | Implement login endpoint and authorization                                       | 2                        |
| 19  | 22.02.2024 | Implement booking record (request) creation with a queue                         | 2                        |
| 20  | 22.02.2024 | Implement balance sheet generation                                               | 3                        |
| 21  | 22.02.2024 | Implement income statement generation                                            | 3                        |
| 22  | 29.02.2024 | Implement pending record request processing                                      | 5                        |
| 23  | 29.02.2024 | Run tests and create protocol with a conclusion of the run                       | 1                        |
| 24  | 29.02.2024 | Evaluate results of the project (as a group)                                     | 3                        |

### Test Cases

## Decide

## Realise

## Control

### Test protocol

### Test conclusion

## Evaluate
