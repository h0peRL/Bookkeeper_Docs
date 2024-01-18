# Project

## Requirements

| **Req. No.** | **Mandatory/Optional** | **Func./Qual./Margin.** | **Requirement**                                                                                |
| :----------- | ---------------------- | :---------------------- | ---------------------------------------------------------------------------------------------- |
| 1            | Mandatory              | Functional              | The app supports multiple users at the same time                                               |
| **2**        | Mandatory              | Marginal                | The app is a .NET 8.0 REST-API (LTS)                                                           |
| **3**        | Mandatory              | Functional              | Data will be stored in an SQL-Database                                                         |
| **4**        | Mandatory              | Functional              | The user can register via HTTP-request                                                         |
| **5**        | Mandatory              | Functional              | The user can log in via HTTP-request                                                           |
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
