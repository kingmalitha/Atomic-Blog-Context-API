# ATOMIC BLOG - CONTEXT API

![Technologies](https://skillicons.dev/icons?i=react,git,github,css,js)

## Introduction

This is a simple prebuilt blog app built with React. We will be using this app to learn about the Context API.

Special thanks to [Jonas Schmedtmann- Ultimate React Course](https://www.udemy.com/course/the-ultimate-react-course/) for the this amazing course. All therory images in this markdown file are also from his course. They are used for educational purposes only. Also prebuilt blog app is from his course.

## WHY CONTEXT API?

- A solution to prop drilling

![Prop Drilling](/mark_img/prop_drilling.png)

- A way to share data between components without having to pass props manually at every level

## WHAT IS THE `CONTEXT` API?

- System to pass data throughout the app `without manually passing props` down the tree.

- Allows us to `broadcast` `global state` to the entire app.

  - `Provider`: Gives all the child components access to value.

  - `Value`: Data that we want to make available (usually state and functions)

  - `Consumers`: All components that read the provided context value.

- What happens when context changes?

  - All the consumers will re-render.

Here is a diagram of how the Context API works:

![How Context API Works](/mark_img/context_api_works.png)
