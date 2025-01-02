# React Native FlatList Performance Issue: Non-memoized renderItem

This repository demonstrates a common performance issue in React Native's `FlatList` component and its solution.
The problem arises when the `renderItem` function returns a component that's not properly memoized. When dealing with large datasets, especially when objects are used as list items, this leads to significant performance degradation because of unnecessary re-renders.  This is due to React's default shallow comparison of props, which doesn't always effectively handle object changes.

The `bug.js` file showcases the problematic code. The `bugSolution.js` file provides a solution using `useMemo` and `React.memo` to optimize the `renderItem` component and enable efficient comparison.

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory in your terminal.
3. Run `npm install` to install dependencies.
4. Run `npx react-native run-android` or `npx react-native run-ios` to run the app.
5. Observe the performance difference between the two examples.