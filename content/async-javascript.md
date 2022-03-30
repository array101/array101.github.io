+++
title = "Async JavaScript"
slug = "async-javascript"
layout = "page.html"
date = 2021-05-08
draft = true
[taxonomies]
tags = ["async", "javascript"]
+++

There are 3 ways work with **asynchronous** code in JavaScript.
- Callbacks
- Promises (ES6; node v4.x, Chrome 32)
- Async / Await (ES7; node v8.x, Chrome 55)

Lets explore each of these for this example use case:
```ts
posts = [
    { title: "Post 1", body: "This is post 1" },
    { title: "Post 2", body: "This is post 2" }
]
```

Promises are immutable, the handler cannot be changed. We are also guaranteed to receive a return value: either what we intended or an error.

https://blog.logrocket.com/the-perfect-architecture-flow-for-your-next-node-js-project/

- async - pushes the operation to run asynchronously
- await - pause execution until myPromise is resolved

## Callbacks
---

Callbacks are unintuitive and hard to debug.


## Promises
---

A `Promise` is always fulfilled - either resolved or rejected.
`Promise` is exclusively used in JS ecosystem: fetch API, axios, etc. So, it's a good idea to learn how to work with it properly.

- A `Promise` enters a 'pending' state until it is resolved or rejected.
- A promise can be created using `new Promise()` constructor

```ts
function createPost(post) {
    // create new promise
    new Promise((resolve, reject) => {
        setTimeout(() => {
            try {
                posts.push(post)
                resolve()
            } catch {
                reject("Error: Something went wrong")
            }
        })
    })
}
createPost({ title: "Post 3", body: "This is post 3" })
    .then(() => console.log("added"))
    .catch(err => console.log(err))
```

- `Promise.all`

Most of the time, we'll be dealing with returned promises from these external packages.

```ts
const promise1 = Promise.resolve('Hello world!')
const promise2 = 10
const promise3 = new Promise((resolve, reject) => {
    setTimeout(resolve, 2000, 'Goodbye')
})
// need to resolve 2 promises; format to JSON -> use data
const promise4 = fetch('https://jsonplaceholder.typicode.com/users').then(res => res.json())

// values = an array of resolved promises
Promise.all([promise1, promise2, promise3, promise4]).then(values => console.log(values))
```

## Async / Await
---

**Await** - waits for an asynchronous process to complete.

NOTE: Async/Await do NOT invoke a seperate thread in the OS.
<!-- Ref: <https://blog.stephencleary.com/2013/11/there-is-no-thread.html> -->

