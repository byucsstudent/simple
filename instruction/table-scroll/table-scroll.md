# Table Scroll

| Employee ID | Full Name | Email Address | Department | Job Title | Office Location | Hire Date | Salary Grade | Performance Rating | Direct Manager | Employment Type | Shift | Remote Status | Last Review |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| EMP-1024 | Jonathan Smith | j.smith@company.com | Engineering | Senior Developer | San Francisco | 2019-05-12 | Grade 8 | Exceeds | Maria Garcia | Full-Time | Day | Hybrid | 2023-12-01 |
| EMP-1025 | Sarah Jenkins | s.jenkins@company.com | Marketing | Brand Manager | New York | 2020-11-03 | Grade 7 | Meets | David Chen | Full-Time | Day | Remote | 2023-10-15 |
| EMP-1026 | Michael Ross | m.ross@company.com | Sales | Account Executive | Chicago | 2021-02-15 | Grade 6 | Exceeds | Sarah Jenkins | Full-Time | Day | On-site | 2024-01-10 |
| EMP-1027 | Emily Davis | e.davis@company.com | HR | Specialist | Austin | 2022-08-30 | Grade 5 | Meets | Robert Wilson | Contract | Day | Hybrid | 2023-09-22 |
| EMP-1028 | Kevin Zhang | k.zhang@company.com | Finance | Analyst | London | 2018-01-22 | Grade 7 | Outstanding | Maria Garcia | Full-Time | Day | Remote | 2023-11-30 |

### Horizontal Scroll Implementation
In GitHub-flavored Markdown (GFM) and standard web rendering, tables with a high column count often exceed the width of the viewport or parent container. To manage this:

1.  **Container Overflow**: Most Markdown parsers wrap tables in a container with `overflow-x: auto;`. This prevents the table from breaking the page layout by providing a horizontal scrollbar.
2.  **Data Preservation**: Horizontal scrolling allows for the display of wide datasets (like the 14 columns above) without forcing line breaks within cells, which maintains the readability of individual data points.
3.  **Responsive Behavior**: On mobile devices, horizontal scrolling is the primary method for navigating complex tables, as vertical stacking would distort the relational structure of the rows and columns.


```masteryls
{"id":"421e0b6d-04de-4519-8c9b-ef7afbe8702c", "title":"Implementing Table Scrolling", "type":"multiple-choice"}
When an HTML `<table>` contains too many columns to fit within its parent container, what is the standard CSS approach to enable horizontal scrolling?

- [ ] Apply `overflow-x: auto` directly to the `<table>` element and set its `display` to `block`.
- [x] Wrap the `<table>` in a container element (like a `<div>`) and apply `overflow-x: auto` to that container.
- [ ] Set the `white-space: nowrap` property on the `<tr>` elements and set the `width` of the `<table>` to `100%`.
- [ ] Add the `scrollable="true"` attribute to the `<table>` tag and set a fixed `max-width` in CSS.
```
