# Lua pairs iterator bug

This repository demonstrates a bug in Lua's `pairs` iterator.  The bug occurs when a table is modified during iteration using `pairs`.  The `pairs` iterator may skip entries if the table structure changes while it's iterating. 

The `bug.lua` file contains the buggy code, and the `bugSolution.lua` file provides a corrected version.

## Bug Description

The `pairs` function iterates over the key-value pairs of a Lua table. If the table's structure is modified (elements added or removed) while `pairs` is iterating, it can cause the iterator to skip entries or behave unpredictably.

## Solution

The solution is to create a copy of the table before iteration, preventing the original table from being modified during the process.