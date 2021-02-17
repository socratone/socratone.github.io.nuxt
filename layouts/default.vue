<template>
  <div>
    <Nuxt />
  </div>
</template>

<style>
:root {
  --color-primary: dodgerblue;
  --color-secondary: deeppink;
  --color-accent: gold;
  --color-body: #333;
  --color-border: gainsboro;
}

html {
  font-size: 62.5%;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 
    Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  height: 100vh;
  margin: 0;
  font-size: 1.8rem;
  color: var(--color-body);
}

*,
*::before,
*::after {
  line-height: 1.5;
  box-sizing: border-box;
  margin: 0;
}

code {
  font-family: Menlo, Monaco, Consolas, "Liberation Mono", "Courier New",
    monospace;
  font-size: 1.5rem;
}

a {
  color: var(--color-body);
  text-decoration: none;
}

img {
  display: block;
}

ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

button {
  outline: none;
}
</style>
