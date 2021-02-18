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
  --color-font-primary: #333;
  --color-font-secondary: #626262;
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
  color: var(--color-font-primary);
}

*,
*::before,
*::after {
  line-height: 1.5;
  box-sizing: border-box;
  margin: 0;
}

h1,
h2,
h3 {
  font-weight: bold;
  margin: 3rem 0 2rem 0;
}

h1 {
  font-size: 2.5rem;
}

h2 {
  font-size: 2.2rem;
}

h3 {
  font-size: 1.8rem;
}

p {
  margin: 2rem 0;
}

code {
  font-family: Menlo, Monaco, Consolas, "Liberation Mono", "Courier New",
    monospace;
  font-size: 1.5rem;
}

a {
  color: var(--color-font-primary);
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
  border: 0;
  padding: 0;
  background: transparent;
  cursor: pointer;
  outline: none;
}
</style>
