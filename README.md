# SQL Server Database Programming — Completed Course Project

My completed CSIS 332 database programming coursework submission, covering retail reporting and a small download-tracking schema. This repository is intended for readers to download, inspect, and work through in SQL Server using the included solutions and exercise instructions. The repository contains T-SQL for joining business entities, calculating sales totals, identifying missing relationships, modifying data, and defining tables, keys, and indexes.

**Deliverables:** chapter-organized [SQL solutions](Queries), four ERD files, and the [complete setup and exercise guide](EXERCISE_GUIDE.md).

**Context:** CSIS 332 final project, based on *Murach's SQL Server 2019 for Developers*, My Guitar Shop exercises, October 2022. The retail database and exercise requirements come from the course/textbook. This case study describes the SQL and design artifacts committed here, without claiming an original retail application or production deployment.

## Download, set up, and test

The [full exercise guide](EXERCISE_GUIDE.md) preserves the original instructions, expected tasks, and chapter-by-chapter workflow. Start there when following the project in detail.

1. Download this repository using **Code → Download ZIP** on GitHub and extract it, or clone the repository.
2. Install SQL Server and SQL Server Management Studio (SSMS). The coursework targets the SQL Server 2019 textbook environment; the exact originally installed versions need confirmation.
3. Obtain the My Guitar Shop starter files from the course/textbook resources referenced in the guide. In particular, `CreateMyGuitarShop.sql` is an external prerequisite and is not bundled in this repository.
4. In SSMS, connect to your SQL Server instance, open `CreateMyGuitarShop.sql`, and execute it. Refresh Object Explorer and confirm that `MyGuitarShop` and its tables appear.
5. Open [Queries](Queries) as a text file. Match its chapter and step labels to the [guide](EXERCISE_GUIDE.md), copy the relevant SQL into an SSMS query window, select `MyGuitarShop` as the database, and execute each exercise separately. Exclude the plain-text chapter headings. Some exercises deliberately produce errors.
6. Compare returned columns, filters, sorting, and totals with the exercise requirements. After inserts, updates, or deletes, use a `SELECT` query to inspect the affected rows. The guide explains when to rerun the starter script to restore the retail dataset.
7. For the download-tracking exercises, create and select a separate database named `MyWebDB`. Follow chapters 10–12 in the guide. Chapters 11 and 12 contain alternative table-creation approaches; use a fresh database for each approach to avoid existing-table conflicts.

Run the data-changing and database-reset exercises in a practice environment. The submission is organized for step-by-step execution, rather than execution of the entire `Queries` file as one batch.

## Technologies

- **Microsoft SQL Server / T-SQL:** joins, aggregate queries, subqueries, DML, DDL, built-in functions, and indexes.
- **SQL Server Management Studio (SSMS):** the documented environment for database setup, query execution, and schema inspection. **Needs confirmation:** exact installed SQL Server and SSMS versions.
- **ER-Assistant document format:** `Final.erd` includes an ER-Assistant file header. A rendered diagram export is not included.

## Architecture and artifacts

The work covers two separate relational database contexts. SSMS is the documented client for executing SQL against SQL Server; there is no application or API layer in the repository.

| Database context | Entities and relationships | Evidence |
| --- | --- | --- |
| **MyGuitarShop — supplied retail database** | Categories and products; customers and addresses; customers, orders, order items, and products. Joins connect these entities for catalog, customer, and sales reporting. | `Queries`, chapters 3–9; [Final.erd](Final.erd) and [ch10.erd](ch10.erd) |
| **MyWebDB — download-tracking exercise** | Users and products each connect to Downloads through `UserID` and `ProductID` foreign keys. Downloads records filenames and download times. | `Queries`, chapters 11–12; [Final pt2.erd](Final%20pt2.erd) and [ch10 pt2.erd](ch10%20pt2.erd) |

The ERD filenames are retained as submitted. The architecture summary above follows the SQL and documented requirements; ERD layout and relationship completeness need visual confirmation.

## Schema and query work

| Skill | Implementation present in `Queries` |
| --- | --- |
| **Relational querying** | Four-table customer/order/item/product join, shipping-address join, product self-join, unused-category outer join, and shipment-status `UNION` (chapter 4). |
| **Reporting and aggregation** | Discount-adjusted line totals, customer totals, category product counts, distinct-product counts, and product totals with a `ROLLUP` grand total (chapters 3 and 5). |
| **Subqueries** | Above-average product pricing, `IN`, `NOT EXISTS`, and a derived table for each customer's largest order (chapter 6). |
| **Data modification** | Category, product, and customer `INSERT`, `UPDATE`, and `DELETE` statements, including deleting child products before their category (chapter 7). |
| **Data types and functions** | `CAST`, `CONVERT`, `ROUND`, date arithmetic, shipping-duration calculations, and last-four-digit display formatting (chapters 8–9). |
| **Schema definition** | Users, Products, and Downloads tables; primary and foreign keys; ZIP-code and foreign-key indexes; defaults; and an `ALTER COLUMN` constraint exercise (chapter 11). Chapter 12 contains a separate table-definition variant. |

## Validation and review notes

**Submission status:** the author identifies this as a completed coursework submission. **Independent review status:** the documentation review inspected the committed SQL but did not rerun it in SQL Server. These are separate statuses. No result screenshots, automated tests, or execution logs are committed; the findings below concern the SQL text, not a judgment about whether the coursework was submitted.

- **Order counts:** chapter 5, steps 4–5 count order IDs after joining to line items, so an order with several items can be counted several times. Validate using `COUNT(DISTINCT o.OrderID)` when measuring orders.
- **Oldest order:** chapter 6, step 6 correlates the minimum date by `OrderID` instead of customer. Correlate by `CustomerID` and define how tied dates should be handled.
- **Download/product join:** chapter 11, step 3 joins `p.ProductID = d.UserID`; the declared relationship uses `d.ProductID`.
- **Schema coverage:** chapter 11 permits null email and last-name values despite the requirements. Chapter 12 declares neither identity columns nor unique email/product-name indexes, and omits the requested download-date and foreign-key indexes in that variant.
- **Execution boundaries:** `Queries` contains plain-text chapter headings, an intentional invalid-column exercise, data-changing statements, and alternative table definitions. It is an exercise collection rather than a single runnable deployment script.

**To independently verify the example:** follow the setup steps above, compare exercise outputs with the guide, and test foreign-key, null, length, and uniqueness behavior. The review findings have not been corrected or runtime-tested as part of this documentation update.

## Scope and limitations

The starter retail database is supplied through the course/textbook resources. Downloading this repository alone does not provide that external setup script. The committed SQL and ERD files document the coursework implementation; the repository does not include an application layer, performance benchmarks, or production deployment evidence.

Index statements demonstrate index creation, with no query-plan or timing evidence. Password updates and card-number formatting are textbook exercises; they do not demonstrate secure authentication or payment-data protection.

## Resume-ready accomplishments

These statements describe the completed coursework and committed implementation:

- Developed T-SQL coursework queries for a retail database using multi-table joins, aggregate reporting, subqueries, and discount-adjusted sales calculations.
- Defined a three-table download-tracking schema in SQL with primary and foreign keys, supporting indexes, defaults, and column-constraint changes.
- Applied SQL Server data conversions, string functions, and date arithmetic to pricing, shipment, and display-formatting exercises.

**Additional details to confirm:** exact SQL Server/SSMS versions, availability of the original execution screenshots, final ERD accuracy, and any later corrections or measured outcomes.
