# My own codepen [find name]

- [ ] insert in markdown


Maybe something like this

    ```html
    <p>My html</p>
    ```

    ```css
    p {
        color: red;
    }
    ```

    ```js
    document.querySelector('p').addEventListener('click', e => {
        alert('hello world!')
    })
    ```

    `!<name>`

And it would take the html, css and js, and format it into an indepedent iframe
which would then run on it's own. If you live edit the html, css and js, it
would rebuild it (css you just re-apply the styling, but that's just
optimisation). Note that you don't need a server whatsoever. It's all static,
running thanks to JavaScript.