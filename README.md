# React useEffect setInterval Memory Leak
This repository demonstrates a common error in React applications: a memory leak caused by improper usage of `setInterval` within the `useEffect` hook.

## Bug Description
The `MyComponent` component uses `setInterval` to update the count state every second.  However, it fails to provide a cleanup function within the `useEffect` hook. This means that on every render, another interval is created, which is not stopped when the component unmounts leading to memory leaks. 

## Solution
The solution involves using the cleanup function provided by the `useEffect` hook to clear the interval when the component unmounts or when the effect's dependencies change.