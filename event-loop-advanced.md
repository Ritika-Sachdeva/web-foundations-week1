# JavaScript Runtime, Event Loop, and Execution Order

When we write JavaScript, it may look like it's running line by line, but there's a lot happening behind the scenes. JavaScript has a runtime that includes a call stack, event loop, and queues that decide how code is executed — especially asynchronous code.

---

##  What is the JavaScript Call Stack?

The **call stack** is like a to-do list for JavaScript. Every time a function is called, it gets added ("pushed") to the top of the stack. Once it's done, it gets removed ("popped") off the stack.

This is how synchronous (normal) code is run — one thing at a time, from top to bottom. JavaScript won't move to the next task until the current one is done.

---

##  Microtasks vs Macrotasks

JavaScript doesn't just run everything on the main stack. When it comes to asynchronous behavior (like Promises, timeouts, etc.), things get scheduled differently — using **microtasks** and **macrotasks**.

###  Microtasks:
- Run **after** the current synchronous code, **before** anything else.
- Examples:
  - `Promise.then()`
  - `queueMicrotask()`

###  Macrotasks:
- Scheduled for a **later time**, run after microtasks are cleared.
- Examples:
  - `setTimeout()`
  - `setInterval()`
  - DOM events

Even though `setTimeout(..., 0)` looks like it should run immediately, microtasks will always finish first.

---

##  Why Promises, queueMicrotask(), and setTimeout() Run Differently

These all run asynchronously, but they are **not equal**:

- `Promise.then()` and `queueMicrotask()` are **microtasks**, so they run **as soon as the call stack is empty**, before any timeouts.
- `setTimeout()` is a **macrotask**. Even if you set a delay of 0ms, it goes to the end of the line — after all microtasks.

So yes, execution order matters, and this is why unexpected results happen if you don't understand this difference.

---

##  How the Event Loop Works

The **event loop** is like a traffic controller.

It keeps watching the call stack and task queues, and follows this cycle:

1. Run all synchronous code (call stack)
2. Run all microtasks in the queue (Promises, queueMicrotask)
3. Pick and run one macrotask (like setTimeout)
4. Repeat the cycle

This cycle goes on non-stop and decides **what runs when** in JavaScript.

---

##  Exercise 1 – Microtasks vs Macrotasks

### Code:

```js
console.log('1');

setTimeout(() => {
   console.log('2');
}, 0);

Promise.resolve().then(() => {
   console.log('3');
});

queueMicrotask(() => {
   console.log('4');
});

console.log('5');
```

**Predicted Output**
1

5

3

4

2

```js
console.log('start');

setTimeout(() => {
   console.log('setTimeout 1');
   Promise.resolve().then(() => console.log('Promise 1'));
}, 0);

setTimeout(() => {
   console.log('setTimeout 2');
}, 0);

Promise.resolve().then(() => console.log('Promise 2'));

console.log('end');
```
**Predicted Output**
start

end

Promise 2

setTimeout 1

Promise 1

setTimeout 2


# MY UNDERSTTANDING FROM THIS TASK

A JavaScript engine is a program that reads and runs (executes) your JavaScript code.

It’s like the brain behind your web page’s behavior — without it, your code is just text sitting there doing nothing.

**EXAMPLE**: _I m speaking Hindi, but my computer only understands Binary_
_So I need a translator who listens to my Hindi and speaks Binary to the computer._

That translator is the JavaScript engine.



## Why JS Engine?

Browsers (like Chrome or Firefox) don’t understand JavaScript directly.
They speak in binary, and JavaScript is human-readable text.

So we need a translator → That’s the JavaScript engine.
The JavaScript engine will:

- Read (Parse) the code
- Convert it to machine code
- Run it on the computer

It’s built into every browser:

- Chrome- V8
- Edge,Opera-	V8
- Firefox-SpiderMonkey
- Safari-	JavaScriptCore
- Node.js-V8 (same as Chrome)

**JavaScript** can only do one thing at a time — it has one main thread called the Call Stack.

It uses something called the Event Loop to manage:

- Sync code (runs immediately)

- Microtasks (Promises)

- Macrotasks (setTimeout, setInterval)

---
## Example: Instagram for async behaviour

## Summary
###  Execution Order

- JavaScript runs code **top to bottom**, starting with all **synchronous code** first.
- Then it processes **microtasks** (like Promises), followed by **macrotasks** (like `setTimeout`).
- The **event loop** controls this order, ensuring the right timing and flow.

---

###  Async Behavior

- Asynchronous tasks (e.g., API calls, timers) are **non-blocking** — they don’t freeze your app.
- These tasks are offloaded and handled via queues, and their results are processed **later**.
- `async/await` and Promises help manage async tasks in a clean, readable way.

---

###  Impact on Real Projects

- Async behavior makes apps **faster, responsive, and user-friendly**, even when waiting for data.
- It prevents UI **freezing or lag**, improving performance and user experience.
- Understanding async flow helps you **debug better**, avoid race conditions, and write scalable code.
