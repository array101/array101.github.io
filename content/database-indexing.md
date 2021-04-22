+++
title = "Glossary"
slug = "glossary"
template = "page.html"
draft = true
[taxonomies]
tags = []
+++


- **database index** - An index is an *ordered* representation of the indexed data. Ex: A phone-book is like having an index on `LastName`. Therefore, it is quicker to find an entry when a person's `lastName` is known, but when only the `firstName` is known, finding that entry is not that quick because it does not have an ordered index of firstName and you need to scan the whole phonebook until you find the firstName.
  - When we're querying database, we're basically searching our data for a subset of data, and searching an ordered input is lot more efficient than searching an unordered input (think binary search - very fast as soon your input is sorted)
  - A db index is actually a B-TREE (Balanced Tree - not Binary) - all node has a left subtree that is smaller than the right subtree and the leaf nodes are at the same depth (hence balanced) - therefore guranteed that it takes same number of steps to find every node. Most of the time in searching is spent in leaf nodes. So, there's also doubly linked list between leaf nodes. The index only contains the values of the columns you actually put the index on.
    - TRADE-OFFS: Reading is **fast**, writing is slow - because every INSERT, UPDATE and DELETE you perform, you also need to insert, update and delete the index needs to be rebalanced - if you have a lot of indexes, your writes are going to be slow.
    - Rule of thumb - have as many indexes as necessary, few as possible
    <img src="https://snipboard.io/j9gN8w.jpg" width="400">
