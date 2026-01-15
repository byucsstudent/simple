# Instruction Title

This is the content of the instruction. It can include **bold text**, _italic text_, <sub>sub</sub>, <sup>super</sup>, and even [links](https://byu.edu).

[GitHub formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)


## Footnotes

Here is a footnote reference.[^1]

[^1]: This is the footnote.

## Emojis

⭐ — Star
📖 — Book

## Lists

- Item 1
- Item 2

* Item 1
* Item 2

- nested
  1. cow
  1. rat
  1. dog
- more
  1. apple
  1. pie

## Color circles

`#0969DA`

## Links

- [Link internal](#mentions)
- [Link quiz](../exampleQuiz/exampleQuiz.md)
- [Link schedule](../../schedule/schedule.md)

## Code Block

```
All the world's a stage,
And all the men and women merely players;
They have their exits and their entrances;
And one man in his time plays many parts,

— Jaques, *As You Like It*, Act II, Scene VII

This renowned monologue serves as an excellent example of Shakespearean dramatic verse, showcasing intricate character portrayal through an extended metaphor and vivid descriptive language. It offers rich opportunities for analyzing thematic development, rhetorical strategies, and the structure of blank verse within a theatrical context.
```

```python
import pandas as pd
import numpy as np

# Sample DataFrame for demonstration of advanced data transformations
df_sales = pd.DataFrame({
    'transaction_id': [1001, 1002, 1003, 1004, 1005, 1006, 1007, 1008, 1009, 1010, 1011, 1012, 1013, 1014, 1015],
    'customer_id': ['CUST001', 'CUST002', 'CUST001', 'CUST003', 'CUST002', 'CUST004', 'CUST001', 'CUST005', 'CUST003', 'CUST004', 'CUST001', 'CUST006', 'CUST002', 'CUST005', 'CUST006'],
    'product_category': ['Electronics', 'Books', 'Electronics', 'Home Goods', 'Books', 'Electronics', 'Apparel', 'Books', 'Home Goods', 'Apparel', 'Electronics', 'Books', 'Apparel', 'Home Goods', 'Electronics'],
    'purchase_amount': [120.50, 45.99, 300.75, 89.99, 15.00, 250.00, 75.25, 60.00, 110.00, 95.50, 450.00, 22.50, 150.00, 70.00, 320.00],
    'purchase_date': ['2023-01-15 10:30:00', '2023-01-16 11:00:00', '2023-01-15 14:15:00', '2023-01-17 09:00:00', '2023-01-16 12:30:00', '2023-01-18 16:00:00', '2023-02-19 10:00:00', '2023-02-20 08:00:00', '2023-03-21 13:00:00', '2023-03-22 17:00:00', '2023-01-25 10:00:00', '2023-02-01 11:00:00', '2023-03-05 12:00:00', '2023-01-28 13:00:00', '2023-02-10 14:00:00'],
    'payment_method': ['Credit Card', 'PayPal', 'Credit Card', 'Debit Card', 'Credit Card', 'PayPal', 'Debit Card', 'Credit Card', 'PayPal', 'Credit Card', 'Credit Card', 'PayPal', 'Debit Card', 'Credit Card', 'PayPal'],
    'shipping_cost': [5.00, 3.50, 7.50, 4.00, 2.50, 6.00, 3.00, 4.50, 5.50, 3.00, 8.00, 2.00, 4.00, 3.50, 7.00]
})
```

```jsx
function comp() {
  return (
    <div ref={containerRef}>
      <ReactMarkdown remarkPlugins={[remarkGfm, remarkEmoji, remarkGithubBlockquoteAlert]} rehypePlugins={[[rehypeRaw], [rehypeMermaid, { mermaidConfig: { theme: 'default' } }]]} components={components}>
        {content}
      </ReactMarkdown>
    </div>
  );
}
```


## Mermaid Diagram

```mermaid
graph TD;
  A[Start] --> B{Is it working?};
  B -- Yes --> C[Great!];
```

## Blockquote and Important Note

> This is a blockquote.

> [!IMPORTANT]
>
> This is an important note that should be highlighted.

## Tables

| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |

## Task Lists

- [x] Feature 1
- [ ] Feature 2
- [ ] Feature 3

## Strikethrough

~~This was mistaken text~~

## Emoji

:smile: :rocket: :tada: :+1:

## Images

![Stock Photo](https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=800&q=80)

## Mentions

@leesjensen - you are needed

## Issue/PR References

#1 - relative

leesjensen/masteryls#1 - absolute

softwareconstruction240/softwareconstruction#297 - absolute

## Autolinked URLs

https://github.com

## Inline HTML

<span style="color: red;">This is red text</span> cow</br>rat

## Collapsed summary

<details>
<summary>My top languages</summary>

| Rank | Languages  |
| ---: | ---------- |
|    1 | JavaScript |
|    2 | Python     |
|    3 | SQL        |

</details>

## Horizontal lines

---
