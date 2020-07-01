# Gatsby Theme Waves

### **I'm not maintaining this project anymore, but I'm working on its spiritual successor: [Code Hike](https://github.com/code-hike/codehike)**

Bring scrollytelling to your mdx. Animate code, images, charts, maps and more as you scroll.

<div align="center">
<a href="https://waves.pomb.us/blog/post">
<img alt="gatsby waves demo" src="https://user-images.githubusercontent.com/1911623/62062600-971a5780-b229-11e9-9c13-cd6a265594d1.gif" />
</a>
<div><a href="https://waves.pomb.us/">See the live demo</a></div>
</div>

The MDX looks like this:

````md
import { CodeWave } from "gatsby-theme-waves"

<CodeWave>

```py
# some code
```

# Some markdown

```py
# more code
```

More markdown

> and more

```py
# and more
```

- ok
- that's enough

</CodeWave>
````

## Installation

You need a Gatsby site with MDX. For example, this is how you add gatsby-theme-waves to a site that uses [gatsby-theme-blog](https://www.npmjs.com/package/gatsby-theme-blog):

1.  Install the theme (and `deepmerge` for merging the theme styles)

    ```sh
    npm install --save gatsby-theme-waves deepmerge
    ```

2.  Add the theme to your `gatsby-config.js` (at the end of the plugin list just in case)

    ```js
    module.exports = {
      plugins: [
        "gatsby-theme-blog",
        "gatsby-theme-waves" // <-- add this
      ]
    };
    ```

3.  Merge the styles: create or edit `src/gatsby-plugin-theme-ui/index.js`

    ```js
    import wavesTheme from "gatsby-theme-waves/src/gatsby-plugin-theme-ui/index";
    import blogTheme from "gatsby-theme-blog/src/gatsby-plugin-theme-ui/index";
    import merge from "deepmerge";

    export default merge(blogTheme, wavesTheme);
    ```

4)  Import `CodeWave` and use it in any MDX file

    ````md
    import { CodeWave } from "gatsby-theme-waves"

    <CodeWave>

    ```py
    # some code
    ```

    # Some markdown

    ```py
    # more code
    ```

    More markdown

    > and more

    ```py
    # and more
    ```

    - ok
    - that's enough

    </CodeWave>
    ````

Your set up should look like [this example](https://github.com/pomber/gatsby-theme-waves/tree/master/blog-demo).

### Code Blocks

By default the lines that changed between two consecutive code blocks will be highlighted. You can change it to highlight the line (and columns) you want:

````md
```js 1:3,6
// highlights line 1,2,3 and 6
```

```js 5[1,3:6],8
// highlights:
// columns 1,3,4,5 and 6 from line 5
// and line 8
```
````

## Coming Soon

- Import code from files
- Better custom code syntax highlighting using theme-ui
- More waves
- More docs
