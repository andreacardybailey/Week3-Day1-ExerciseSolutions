### Solutions for the Bookstore Inventory Management Exercise:

* * * * *

#### 1\. Adding a Book

```javascript

function addBook(inventory, book) {
    inventory.push(book);
    return inventory;
}
```

* * * * *

#### 2\. Selling a Book

```javascript

function sellBook(inventory, bookTitle) {
    const book = inventory.find(b => b.title === bookTitle && !b.sold);
    if (book) {
        book.sold = true;
    }
    return inventory;
}
```

* * * * *

#### 3\. Removing Last Added Book

```javascript

`function removeLastAdded(inventory) {
    inventory.pop();
    return inventory;
}
```

* * * * *

#### 4\. List all Authors

```javascript

`function listAllAuthors(inventory) {
    const authors = inventory.map(b => b.author);
    return [...new Set(authors)]; // Returns unique authors
}
```

* * * * *

#### 5\. Total Inventory Value

```javascript

function totalValue(inventory) {
    const unsoldBooks = inventory.filter(b => !b.sold);
    return unsoldBooks.reduce((acc, book) => acc + book.price, 0);
}
```

* * * * *

#### 6\. First 3 Expensive Books

```javascript

function top3Expensive(inventory) {
    const unsoldBooks = inventory.filter(b => !b.sold);
    const sortedBooks = unsoldBooks.sort((a, b) => b.price - a.price); // Descending order based on price
    const top3 = sortedBooks.slice(0, 3);
    return top3.map(b => b.title);
}
```

* * * * *

#### Testing the functions:

You can test each function using the provided `inventory`:

```javascript

const inventory = [
  { title: 'Harry Potter', author: 'J.K. Rowling', price: 10.99, sold: false },
  { title: 'Lord of the Rings', author: 'J.R.R. Tolkien', price: 15.99, sold: true },
  { title: 'Dune', author: 'Frank Herbert', price: 12.99, sold: false },
];

console.log(addBook(inventory, { title: 'To Kill a Mockingbird', author: 'Harper Lee', price: 9.99, sold: false }));
console.log(sellBook(inventory, 'Dune'));
console.log(removeLastAdded(inventory));
console.log(listAllAuthors(inventory));
console.log(totalValue(inventory));
console.log(top3Expensive(inventory));`
```

Each `console.log` should output the expected result for each function.
