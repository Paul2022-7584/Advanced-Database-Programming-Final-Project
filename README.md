# SQL Server Database Programming Case Study

A coursework-based SQL portfolio covering retail reporting and a small download-tracking schema. The repository contains T-SQL for joining business entities, calculating sales totals, identifying missing relationships, modifying data, and defining tables, keys, and indexes.

**Outcome:** a chapter-organized [SQL implementation collection](Queries) and four ERD files. The strongest evidence is the submitted SQL itself; execution results and complete exercise correctness have not been verified.

**Context:** CSIS 332 final project, based on *Murach's SQL Server 2019 for Developers*, My Guitar Shop exercises, October 2022. The retail database and exercise requirements come from the course/textbook. This case study describes the SQL and design artifacts committed here, without claiming an original retail application or production deployment.

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

## Validation and known gaps

**Review status:** repository contents were inspected; SQL was not executed against SQL Server. No result screenshots, automated tests, or execution logs are committed. The following are static-review findings, not observed runtime results.

- **Order counts:** chapter 5, steps 4–5 count order IDs after joining to line items, so an order with several items can be counted several times. Validate using `COUNT(DISTINCT o.OrderID)` when measuring orders.
- **Oldest order:** chapter 6, step 6 correlates the minimum date by `OrderID` instead of customer. Correlate by `CustomerID` and define how tied dates should be handled.
- **Download/product join:** chapter 11, step 3 joins `p.ProductID = d.UserID`; the declared relationship uses `d.ProductID`.
- **Schema coverage:** chapter 11 permits null email and last-name values despite the requirements. Chapter 12 declares neither identity columns nor unique email/product-name indexes, and omits the requested download-date and foreign-key indexes in that variant.
- **Execution boundaries:** `Queries` contains plain-text chapter headings, an intentional invalid-column exercise, data-changing statements, and alternative table definitions. It is an exercise collection rather than a single runnable deployment script.

**Validation still needed:** execute individual exercises in disposable databases; compare results with expected rows and totals; test foreign-key, null, length, and uniqueness behavior; and retain outputs. No fixes or successful test outcomes are claimed here.

## Reproduction and limitations

1. Obtain the course/textbook My Guitar Shop starter files, including `CreateMyGuitarShop.sql`; they are referenced by the original guide but are not included here.
2. Use a disposable SQL Server environment and SSMS. Initialize the supplied retail database before running its exercises.
3. Copy individual SQL blocks from `Queries`, excluding chapter headings. Run the MyWebDB work separately from MyGuitarShop and review the alternative chapter 11–12 definitions before creating tables.

The repository does not establish performance improvements, production scale, deployment, or full completion of every requirement. Index statements demonstrate index creation, with no query-plan or timing evidence. Password updates and card-number formatting are textbook exercises; they do not demonstrate secure authentication or payment-data protection.

The [original exercise guide](https://github.com/Paul2022-7584/Advanced-Database-Programming-Final-Project/blob/de609810b4c56570c2550a11b3a392daba74e94f/README.md) remains available in project history.

## Resume-ready accomplishments

These statements describe committed artifacts, without claiming validated execution or business impact:

- Developed T-SQL coursework queries for a retail database using multi-table joins, aggregate reporting, subqueries, and discount-adjusted sales calculations.
- Defined a three-table download-tracking schema in SQL with primary and foreign keys, supporting indexes, defaults, and column-constraint changes.
- Applied SQL Server data conversions, string functions, and date arithmetic to pricing, shipment, and display-formatting exercises.

**Needs confirmation before stronger claims:** personal authorship versus supplied solution code; which exercises were successfully executed; availability of the original submission/screenshots; final ERD accuracy; and any later corrections or measured outcomes.
