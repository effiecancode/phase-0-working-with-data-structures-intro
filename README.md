# Introduction to Working with Data Structures

## Learning Goals

- Compare collection data types to other data types
- Define `Array`
- Define `Array` element
- Define `Array` index
- Define `Object`
- Define `Object` key
- Define `Object` value
- Demonstrate nesting of collection data structures

## Introduction

Thus far, we've been storing simple data in our variables, values like:

- `String`s
- `Boolean`s
- `Number`s
- etc.

But sometimes we want to refer to a _collection_ of values by a common name.
This is very natural in conversation: we know "The Beatles" refer to four guys
from Liverpool who sang "I Wanna Hold Your Hand." "Grocery List" is something
that contains multiple small elements that we identify by "the third item on my
grocery list, or the last item on my grocery list." Ordered lists in JavaScript
are called "Arrays."

![Grocery List](https://curriculum-content.s3.amazonaws.com/phase-0/working-with-data-structures-intro/grocery-list.png)

Another collection type we know about from daily life are dictionaries: we use
one thing to "look up" a value. We "look up" the word "computer" in a real
dictionary and we are "pointed to" a long `String` that tells us what the word
means. Lookup tables, or dictionaries, in JavaScript, are called "Objects."

![Dictionary](https://curriculum-content.s3.amazonaws.com/phase-0/working-with-data-structures-intro/dictionary.png)

Learning to store and to work with the data held in data structures will be the
focus of this section. In this lesson, we'll give you a broad, conceptual
introduction to collection data types.

## Compare Collection Data Types to Scalar Data Types

`String`s and `Number`s are scalar data types, they can be put on a scale. A
collection type holds multiple pieces of data and allows us to talk about the
collection as an _abstraction_. "The Beatles" is an _abstraction_ used to refer
to the individuals John, Paul, George, and Ringo. Because collection types can't
be put on a scale, they **_are not_** called scalar data types.

## Define `Array`

An `Array` is a collection that holds multiple pieces of data under a single
name ("Countries", "Fast and the Furious Movies"). In daily life, we call them
"lists."

**The Beatles**

| Index | Data              |
| ----- | ----------------- |
| 0     | "John Lennon"     |
| 1     | "Paul McCartney"  |
| 2     | "Ringo Starr"     |
| 3     | "George Harrison" |

or

**Groceries**

| Index | Data                 |
| ----- | -------------------- |
| 0     | "Parsnips"           |
| 1     | "English Toffee"     |
| 2     | "Milk"               |
| 3     | "Sprouted Rye Bread" |

The individual _elements_ that make up this collection (or list) are identified
by an _index_.

![Beatles](https://curriculum-content.s3.amazonaws.com/phase-0/working-with-data-structures-intro/beatles.png)

It might seem strange that we start our list at `0` instead of `1`. Programmers
like `0` and most programming languages start their index at `0`. Otherwise,
it's pretty much a list like you've been making most of your life.

To define this "list" in JavaScript we would type:

```js
const theBeatles = [
  "John Lennon",
  "Paul McCartney",
  "Ringo Starr",
  "George Harrison",
];
```

You provide a name (`theBeatles`), an assignment operator (`=`) and then a list
of data, separated by commas, that should go in the `Array`, wrapped in `[]`.
Each bit of information is often a scalar value, but it could also be another
collection (more on that later).

## Define `Array` Element / Member

The individual pieces of data inside an `Array` are called _elements_. Some
people also call the _elements_ the _members_. In a collection of
`theBeatles`, the `String` `"George Harrison"` is an _element_.

## Define `Array` Index

`Array`s provide a number that identifies each _element_ called an _index_. The
index for the _element_ `"Ringo Starr"` above is `2`.

We'll cover adding, removing, retrieving, and deleting _elements_ via their
_index_ in another lesson.

## Define `Object`

Another way of thinking about `Array`s is that they are like tables that have an
identifier that is a `Number`. If we let the identifier be a `String` _instead_
of a `Number`, then we'd basically be describing an `Object`.

What if we wanted to take our list of the Beatles and  describe each member not
by some `Number` _index_, but rather by the instrument they played in the band?
As a table this might look like:

| Instrument      | Beatle            |
| --------------- | ----------------- |
| "Rhythm Guitar" | "John Lennon"     |
| "Bass"          | "Paul McCartney"  |
| "Drums"         | "Ringo Starr"     |
| "Lead Guitar"   | "George Harrison" |

An `Object` is a collection data type that holds multiple pieces of data under a
collected name whose members can be read and updated by using a _key_ instead of
an _index_. In daily conversation we use _keys_ to retrieve _values_ all the
time: "Who was the guy who played **drums** in **The Beatles**?"

We can think of `Object`s like a table that looks like this:

| Key          | Value                                           |
| ------------ | ----------------------------------------------- |
| "liverpool"  | "The Beatles"                                   |
| "manchester" | "The Smiths"                                    |
| "coventry"   | "Delia Derbyshire and the BBC Radiophonic Band" |
| "london"     | "Ziggy Stardust and the Spiders from Mars"      |

To define this "table" in JavaScript we would type:

```js
const englishBandsByCity = {
  liverpool: "The Beatles",
  manchester: "The Smiths",
  coventry: "Delia Derbyshire and the BBC Radiophonic Band",
  london: "Ziggy Stardust and the Spiders from Mars",
};
```

You provide a name (`englishBandsByCity`), an assignment operator (`=`) and then
a list of pairs, separated by commas, that should go in the `Object`, wrapped in
`{}`. Each pair should have a key, a colon (`:`), and a value. A value is often
a scalar value, but it could be another collection; more on that later.

## Define `Object` Key

`Object`s are like tables that have a name that is a piece of data, typically a
`Symbol` or a `String`. This identifier is called a _key_.

## Define `Object` Value

The value that's returned from asking an `Object` what a given _key_ points to
is known as the key's _value_.

We'll cover adding, removing, retrieving, and deleting _values_ via their
_key_ in another lesson.

## Demonstrate Nesting of Collection Data Structures

Now that you know about `Array`s (grocery lists, band members, todo lists) and
`Object`s (abbreviation to full name lookup, a stock symbol to trading value
lookup, instrument to band member name lookup) you might be a bit unimpressed.
"Surely the world's data needs are more complex than simple lists and lookup
tables," you might exclaim.

You'd be right, but the amazing thing about collections is that they can
contain _other_ collections as part of a process called _nesting_. Can you
imagine an `Array` of `Object`s? Or an `Object` of `Arrays` of `Object`s of
`Array`s? You can cover a staggeringly huge model of data with nesting of these
two data types.

We want to provide a really complex example of `Array`s and `Object`s working
together. Most programming texts don't share this concept this early and it
makes "nesting" sound scary and complex. We're going to give you a short
demonstration here so that you can see why you want to have these complex data
structures. The details on how to build them etc... will come in later lessons.

The _elements_ in an _Array_ and the _values_ in an _Object_ can be `Object`s or
`Array`s _themselves_. This leads to "nesting" such that you could build a
complex data structure like the following:

```js
const englishMusicByCity = {
  manchester: [
    {
      bandName: "The Smiths",
      memberNames: ["Morrissey", "Johnny", "Andy", "Mike"],
    },
    {
      bandName: "Joy Division",
      memberNames: ["Peter", "Stephen", "Bernard", "Ian"],
    },
  ],
};
```

The _abstraction_ `englishMusicByCity` hides the complexity in that piece of data.

As a peek ahead, we can use bracket notation (`[]`) to "dig into" this nested
collection and get interesting information out:

```js
englishMusicByCity["manchester"][0]["bandName"]; //=> "The Smiths"
englishMusicByCity["manchester"][0]["memberNames"]; //=> ["Morrissey", "Johnny", "Andy", "Mike"]

console.log(
  `There were ${englishMusicByCity["manchester"][0]["memberNames"].length} members in ${englishMusicByCity["manchester"][0]["bandName"]}`
);
//=> "There were 4 members in The Smiths"
```

## Conclusion

This has been a broad tour of JavaScript's collection data types, `Object`
and `Array`. Individually, they are data structures that can hold list- and
dictionary-like data. Amazingly, they can even _hold each other_ — and that
means we can make very complex data structures from them! We'll practice with
these types in the following lessons!
