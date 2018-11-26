
# Responsive Styles

Often when working on responsive layouts, it's useful to adjust styles across a singular dimension –
such as font-size, margin, padding, and width. Instead of manually managing media queries and adding nested style objects throughout a code base,
styled-system offers two convenient syntaxes for adding responsive styles with a mobile-first approach.

The first is a short hand array syntax, while this syntax can seem odd at first, it can become a powerful way to manage responsive
typography and layouts.

```jsx
<Box
  width={[
    1,    // 100% below the smallest breakpoint
    1/2,  // 50% from the next breakpoint and up
    1/4   // 25% from the next breakpoint and up
  ]}
/>

// responsive font size
<Box fontSize={[ 1, 2, 3, 4 ]} />

// responsive margin
<Box m={[ 1, 2, 3, 4 ]} />

// responsive padding
<Box p={[ 1, 2, 3, 4 ]} />
```

The second, is an object map which takes a breakpoints object from the provided theme:

```javascript
  theme: {breakpoints: {xs: 0, sm: '40em', md: '50em', lg: '60em'}},
```

```jsx
<Box
  width={{
    xs: 1,    // 100% from the 'xs' breakpoint
    sm: 1/2,  // 50% from the 'sm' breakpoint and up
    md: 1/4   // 25% from the 'md' breakpoint and up
  }}
/>

// responsive font size
<Box fontSize={{ xs: 1, sm: 2, md: 3, lg: 4 }} />

// responsive margin
<Box m={{ xs: 1, sm: 2, md: 3, lg: 4 }} />

// responsive padding
<Box p={{ xs: 1, sm: 2, md: 3, lg: 4 }} />
```

All style utilities add props that accept both syntaxes as values for mobile-first responsive styles.
