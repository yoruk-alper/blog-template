---
title: My second Blog Post
description: Learning how to use @nuxt/content to create a blog
img: https://images.unsplash.com/photo-1631507467986-bc98ba4ed1b3?ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyMHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60
alt: my second blog post
author:
  name: Benjamin
  bio: All about Benjamin
  image: https://images.unsplash.com/photo-1631507467986-bc98ba4ed1b3?ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyMHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=60
---

## This is a heading

This is some more info

### This is a sub heading

This is some more info

### This is another sub heading

This is some more info

## This is another heading

This is some more info

# My first blog post

Welcome to my first blog post using content module

<div class="p-4 mb-4 text-white bg-blue-500">
  This is HTML inside markdown that has a class of note
</div>

```js[my-first-blog-post.md]
export default {
  nuxt: 'is the best'
}
```
```html
<p>code styling is easy</p>
```

<info-box>
  <template #info-box>
    This is a vue component inside markdown using slots
  </template>
</info-box>

[comment]: <> (<author :author="author"></author>)
