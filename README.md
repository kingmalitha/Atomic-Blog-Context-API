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

## HOW TO USE CONTEXT API?

1. Create a context

```js
import { createContext } from "react";

const PostContext = createContext();
```

2. Wrap the components that need access to the context in the `Provider` component and pass the value to the `value` prop.

```js
import { PostContext } from "./contexts/PostContext";

function App() {
  return (
    <PostContext.Provider
      value={{
        posts: searchedPosts,
        onAddPost: handleAddPost,
        onClearPosts: handleClearPosts,
        searchQuery,
        setSearchQuery,
      }}
    >
      <div className='App'>
        <Navbar />
        <div className='content'>
          <Posts />
        </div>
      </div>
    </PostContext.Provider>
  );
}
```

3. In the components that need access to the context, use the `useContext` hook to get the value.

```js
import { useContext } from "react";

function Results() {
  const { posts } = useContext(PostContext);
  return <p>🚀 {posts.length} atomic posts found</p>;
}
```

- Important!. In here context can be used in any children components, but not in the App component itself. Because App component is not a child of the Provider component. So If you try to access it you get `undefined` values.
