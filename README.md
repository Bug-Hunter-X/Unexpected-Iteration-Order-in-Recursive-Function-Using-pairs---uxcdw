# Lua Pairs Iteration Bug

This repository demonstrates a potential issue with Lua's `pairs` iterator when used in recursive functions with tables containing non-numeric keys.  The `pairs` iterator does not guarantee a specific iteration order, which can lead to unexpected behavior if the order is assumed.

The `bug.lua` file contains code that illustrates this problem. The `bugSolution.lua` file shows a potential solution using a sorted iteration approach.

## Bug Description

The recursive function `foo` iterates through a nested table. The expected behavior depends on a consistent iteration order; however, `pairs` does not provide this guarantee.  This can cause the function to produce unpredictable results depending on the Lua interpreter's internal implementation.

## Solution

The solution employs a method that guarantees a consistent iteration order, such as sorting the keys before iteration, to address the unpredictability of the `pairs` iterator. This approach ensures that the function behaves consistently across different Lua interpreters.