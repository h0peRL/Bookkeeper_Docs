# Documentation

## Research

### Sources

### Requirements

| **Req. No.** | **Mandatory/Optional** | **Func./Qual./Margin.** | **Requirement**                                                                                |
| :----------- | ---------------------- | :---------------------- | ---------------------------------------------------------------------------------------------- |
| 1            | Mandatory              | Functional              | The app supports multiple users at the same time                                               |
| 2            | Mandatory              | Marginal                | The app is a .NET 8.0 REST-API (LTS)                                                           |
| 3            | Mandatory              | Marginal                | Data will be stored in an SQL-Database                                                         |
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
| 14           | Mandatory              | Marginal                | The program and documentation should be in English                                             |
| 15           | Mandatory              | Marginal                | There should be a glossary with German translations                                            |

### Tech Stack

## Plan

### Work Packages

| Nr. | Due Date   | Description                                                                      | Estimated Time (45 min.) |
| --- | ---------- | -------------------------------------------------------------------------------- | ------------------------ |
| 0   | 25.01.2024 | Create table with work packages                                                  | 2                        |
| 1   | 18.01.2024 | Set up documentation                                                             | 5                        |
| 2   | 18.01.2024 | Set up project                                                                   | 3                        |
| 3   | 18.01.2024 | Set up repositories                                                              | 2                        |
| 4   | 18.01.2024 | Define detailed requirements                                                     | 2                        |
| 5   | 01.02.2024 | Set up shared (prod.) DB (with users)                                            | 7                        |
| 6   | 25.01.2024 | Research Technologies                                                            | 5                        |
| 7   | 25.01.2024 | Create detailed MVC class diagram in VP                                          | 15                       |
| 8   | 25.01.2024 | Decide about technologies to use                                                 | 3                        |
| 9   | 25.01.2024 | Set up test DB (with users)                                                      | 5                        |
| 10  | 25.01.2024 | Set up linter and styling rules                                                  | 3                        |
| 11  | 01.02.2024 | Set up CI pipelines                                                              | 5                        |
| 12  | 01.02.2024 | Set up pre-commits                                                               | 3                        |
| 13  | 01.02.2024 | Write test cases for every requirement with test env. definition (documentation) | 8                        |
| 14  | 01.02.2024 | Write unittests from test cases (for model only!)                                | 6                        |
| 15  | 25.01.2024 | Integrate EF as ORM with DB                                                      | 5                        |
| 16  | 25.01.2024 | Create class and method bodies from class diagram                                | 2                        |
| 17  | 22.02.2024 | Implement registration endpoint                                                  | 2                        |
| 18  | 22.02.2024 | Implement login endpoint and authorization                                       | 4                        |
| 19  | 22.02.2024 | Implement booking record (request) creation with a queue                         | 2                        |
| 20  | 22.02.2024 | Implement balance sheet generation                                               | 3                        |
| 21  | 22.02.2024 | Implement income statement generation                                            | 3                        |
| 22  | 29.02.2024 | Implement pending record request processing                                      | 5                        |
| 23  | 29.02.2024 | Run tests and create protocol with a conclusion of the run                       | 2                        |
| 24  | 29.02.2024 | Evaluate results of the project (as a group)                                     | 3                        |
| -   | -          | Total estimated time effort in lessons:                                          | **105**                  |

???+ info "Total Time Spent (estimate)"

Here is the calculation of how many lessons the project should take to implement. Please note, that a single lesson equals 45 minutes

```
team members: 3
total weeks: 7
lessons per week: 5
lessons per member: 7 * 5 = 35
total lessons: 35 * 3 = 105
```

**The total amount of lessons should be 105** as every one of the 3 members works 5 lessons per week over the course of 7 weeks.

### Test Cases

| Testf.<br />Nr. | Anf.<br />Nr. | Voraussetzungen                                                            | Testumgebung     | Eingabe/Aktion                                                        | Erw. Ausgabe                  |
| --------------- | ------------- | -------------------------------------------------------------------------- | ---------------- | --------------------------------------------------------------------- | :---------------------------- |
| 1.1             | 3             | Unittest for multifuctionality is crated.                                  | VS, .NET 8.0 LTS | Start the unittest which is used to test the multiuser functionality. | Unittest is succesfull.       |
| 2.1             | 4             | Backend is up and running, correct API endpoint is used: .../auth/register | Postman, Swagger | name: youruname<br />password: yourpw                                 | HTTP 200 succes. User created |
|                 |               |                                                                            |                  |                                                                       |                               |
|                 |               |                                                                            |                  |                                                                       |                               |
|                 |               |                                                                            |                  |                                                                       |                               |
|                 |               |                                                                            |                  |                                                                       |                               |
|                 |               |                                                                            |                  |                                                                       |                               |
|                 |               |                                                                            |                  |                                                                       |                               |
|                 |               |                                                                            |                  |                                                                       |                               |

## Decide

### Database Type and Engine

At the very beginning of the project we were thinking about using a realtime NoSQL database such as [Firebase](https://firebase.google.com/docs/database) to avoid having to deal with failed transactions. That would have worked by attaching observers to certain nodes (JSON elements) in the database and subscribing them to update events.

However, we decided to go with a relational database in the end, so that we can avoid redundancy. Our final decision on this subject came down to [Microsoft SQL Server 2022 Express](https://www.microsoft.com/de-de/download/details.aspx?id=104781). We chose that engine due to its range of feature and our experience with it.

### Production Database Hosting

Initially, we thought that we could simply spin up a database with our student accounts on [Microsoft Azure](https://azure.microsoft.com/en-us/), the pricing however, turned out to be very inconvenient. For our use case it was way too expensive and this option was out of question in no time after we found out about that.

After looking for an alternative host for Microsoft SQL Servers, one of our team members was kind enough and offered to host the database privately on his own server at home. So after setting things up and forwarding the port of the SQL server, the database was ready for use.

### Development Database Options

For development and testing purposes we decided to use a secondary database with fake data on it to be able to swiftly reproduce scenarios and different use cases without potentially breaking the main production database. That secondary database should consist of a docker container with a docker image that already has the fake test data in it. This way we can just reset everything when restarting that container if it has impersistent storage.

### Documentation Site

In terms of hosting the documentation there were interesting discussions as well. They were mostly about whether we should stay with [Docusaurus](https://docusaurus.io/) (a technology we all know from previous projects) or if we should try out something new as an alternative. This is due to Docusaurus being a struggle to fully integrate and automate with GitHub-Pages.

As a replacement we found several other tools. Most of them were sadly even less convenient or just overly complicated compared to docusaurus. One of the top candidates was [Sphinx](https://www.sphinx-doc.org/en/master/), but it uses a very odd syntax over the regular Markdown everyone in the team is used to.

When looking for a potential host for it we found [Read the Docs](https://about.readthedocs.com/?ref=readthedocs.com). It can even fully automate previews and deployments from a GitHub repository by simply setting up a Webhook in it. This feature spared us the creation of a dedicated workflow and the debugging of it, which took a good while with Docusaurus originally. So this is the host we went with for the documentation, instead of GitHub-Pages.

While skimming through the documentation of the new host, we found out that it also works with a Markdown based framework called [MkDocs](https://www.mkdocs.org/). After reading up a bit on MkDoc's customization possibilities we found the [Material Theme for MkDocs by Squidfunk](https://squidfunk.github.io/mkdocs-material/) to be suitable for our needs. It provides more or less the same features as Docusaurus, just without the complications we had. As so, our final decision regarding the documentation side of things was to use MkDocs with the Material Theme and host it on Read the Docs.

### Linting and Linters

When it comes to linting C#, dotnet has a default formatter that can also enforce some style rules and patterns. The range of options one can choose from is not very wide, however. To have more freedom in terms of details and choice, we decided to integrate [stylecop](https://marketplace.visualstudio.com/items?itemName=ChrisDahlberg.StyleCop), a static code analyzer for C#, into our project.

### REST API Framework

So we won't have to create our entire REST API from scratch, we decided to use a framework that is part of the dotnet ecosystem. We will be using an [ASP.NET Core Web API](https://dotnet.microsoft.com/en-us/apps/aspnet/apis) to get things going.

Another reason for our choice was the compatibility and easy integration with the Entity Framework

### Testing REST Endpoints

To test and develop the endpoints of the REST API we will be using a workspace on [Postman](https://www.postman.com/). It is a tool that supports automated testing of API endpoints with lots of utility. The reason we went with this option is that all of us worked with it several times before.

### Handling SQL Transaction Errors

Considering the fact that our app will be booking digital money, we want rule out any possibility of anomalies that can alter the total amount of money in the system. Especially since our app allows multiple users to use it at the same time.

We put these measures into place to handle conflicting transactions:

- avoid common columns by calculating total with past records (no common writes)
- queue record requests for compatibility check (warning/error can be raised)

## Realise

## Control

### Test Protocol

### Conclusion

## Evaluate
