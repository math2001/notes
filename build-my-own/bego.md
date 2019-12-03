# Bego

An alternative to Hugo. Written in Go of course.

- [ ] everything is accessible from everywhere, and it is the only way to
  access anything. For special pages, only key characteristics are given. For
  example, the data of the page /post/my-post.md only differs on one field,
  .Specific (please find a better name), which contains just the path of the
  thing, maybe the section, name, but that's it. The least amount of duplicate
  information as possible. Then, you just use template logic to find the
  information you need
- [ ] implements {{ debug . }}, where it prints every field with it's
  corresponding value in a nicely formatted pre. I don't care how many hoops
  you have to jump through to get to this. Just do it.
- [ ] it serves lives
- [ ] it's fast
- [ ] command to deploy to github pages
- [ ] resource manager: while live serving, you link to the static files `<link
  href="..." />`, but when building, you inline them. And of course, it's
  minified
