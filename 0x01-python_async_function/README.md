Async IO is a concurrent programming design that has received dedicated support in Python, evolving rapidly from Python 3.4 through 3.7, and probably beyond.

You may be thinking with dread, “Concurrency, parallelism, threading, multiprocessing. That’s a lot to grasp already. Where does async IO fit in?”

This tutorial is built to help you answer that question, giving you a firmer grasp of Python’s approach to async IO.

Here’s what you’ll cover:

Asynchronous IO (async IO): a language-agnostic paradigm (model) that has implementations across a host of programming languages

async/await: two new Python keywords that are used to define coroutines

asyncio: the Python package that provides a foundation and API for running and managing coroutines

Coroutines (specialized generator functions) are the heart of async IO in Python, and we’ll dive into them later on.

Note: In this article, I use the term async IO to denote the language-agnostic design of asynchronous IO, while asyncio refers to the Python package.

Before you get started, you’ll need to make sure you’re set up to use asyncio and other libraries found in this tutorial.

Free Bonus: 5 Thoughts On Python Mastery, a free course for Python developers that shows you the roadmap and the mindset you’ll need to take your Python skills to the next level.
