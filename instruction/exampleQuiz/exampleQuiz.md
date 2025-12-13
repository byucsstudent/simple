# Example Quiz

This demonstrates how to write quizzes in Mastery LS format.

```masteryls
{"id":"a347b1df-9f80-4d3e-8585-a64bc1f76a5f", "title":"Multiple choice", "type":"multiple-choice", "body":"Simple **multiple choice** question" }
- [ ] This is **not** the right answer
- [x] This is _the_ right answer
- [ ] This one has a [link](https://cow.com)
- [ ] This one has an image ![Stock Photo](https://images.unsplash.com/photo-1506744038136-46273834b3fb?auto=format&fit=crop&w=400&q=80)
```

```masteryls
{"id":"d3faa8e4-03ee-4bc2-bfe4-4f448940daa0", "title":"Multiple select", "type":"multiple-select", "body": "A **multiple select** question can have multiple answers. Incorrect selections count against correct ones when calculating the correct percentage." }
- [ ] This is **not** the right answer
- [x] This is _the_ right answer
- [ ] This is **not** the right answer
- [x] Another right answer
- [ ] This is **not** the right answer
```

```masteryls
{"id":"c42bd013-a1ac-4cf1-b425-ae78bd753d8f", "title":"Essay", "type":"essay", "body":"Simple **essay** question" }
```

```masteryls
{"id":"e5e7cc56-0173-4cda-8938-a27235a33bc3", "title":"File submission", "type":"file-submission", "body":"Simple **submission** by file", "allowComment":true  }
```

```masteryls
{"id":"18a20532-4e47-42e7-ac2c-cffc3c35f8c5", "title":"URL submission", "type":"url-submission", "body":"Simple **submission** by url", "allowComment":true }
```
