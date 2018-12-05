# Designing Object Oriented Applications

## Learning Goals

## Introduction

In the earlier [methods][methods] lab, we saw that using `get` and `set` allows
us to differentiate between 'public' methods (all methods that deal with
input/output of a `class`) and 'private' methods (internal methods, not to be
used outside the `class`). In JavaScript, unlike other Object Oriented
languages, all `class` properties and methods are accessible outside of the
`class`. However, if we choose to, we can apply designs that help keep our code
clean and understandable, and therefore, easier to maintain.

Now that we have reviewed how to build small, multi class applications, we see
that it is possible to represent a wide array of relationships between `class`
objects. But, just as it is with the structure of a `class`, how we design
`class` relationships matters.

In this lesson, we are going to briefly go over some design concepts that
will keep your entire application structured in a way that is easy to understand

## Single Responsibility Principle

## Who is Responsible For Maintaining Relationships

We've previously touched on the concept of `class` dependency. A `Book` `class`,
for instance, might utilize properties and methods from `Author` and `Genre`
`class`es. The `Book` `class` is _dependent_ on the other. It could be written
the other way around. What if the `Author` `class` kept track of `Book`s?
Consider the following alternative:

```js
class Book {
	constructor(title, genre, publishingDate) {
		this.title = title;
		this.genre = genre;
		this.publishingDate = publishingDate;
	}
}

class Author {
	constructor(firstName, lastName, books = []) {
		this.firstName = firstName;
		this.lastName = lastName;
		this._books = books;
	}

	get books() {
		return this._books;
	}

	set books(booksArray) {
		this._books = booksArray;
	}

	set addBook(book) {
		this._books.push(book);
	}
}

let denisJohnson = new Author('Denis', 'Johnson');
let trainDreams = new Book('Train Dreams', 'Historical Fiction', '2002');

denisJohnson.addBook(trainDreams);
denisJohnson;
```

In the above code, the `Author` class keeps track of w

```
class Song {
  constructor() {

  }
}

class Album {
  constructor() {

  }
}

class Artist {
  constructor() {

  }
}
```

## Only Know Your Immediate Neighbors

##

Single Responsibility Principle

Open/Closed Principle

Liskov Substitution Principle

Interface Segregation Principle

Dependency inversion Principle

[methods]:
