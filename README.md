# React Native: Accessing State Before Component Mount

This repository demonstrates a common error in React Native: attempting to access component state or props before the component has fully mounted. This often occurs when performing asynchronous operations within lifecycle methods such as `componentDidMount`.

## Problem

The `bug.js` file showcases the problematic code. Asynchronous data fetching is performed in `componentDidMount`, but the component attempts to access and render the fetched data before the `setState` call completes.

## Solution

The `bugSolution.js` file provides a corrected version.  It uses conditional rendering to only display the data once it's available, thus preventing the error.  Additionally,  more robust error handling is included. 

## How to reproduce the error

1. Clone this repo
2. Run `npm install`
3. Run `npx react-native run-android` (or iOS equivalent)
4. Observe the error in the console and the app behavior

## How to fix it

Review the `bugSolution.js` for the corrected implementation.  The key changes are:
    * Conditional rendering: only render components when data is available.
    * Proper error handling. 
    * Using `useEffect` hook (for functional components).