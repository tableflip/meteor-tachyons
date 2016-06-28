# Meteor and Tachyons

How to make the web look nice with [Tachyons CSS], from the comfort of a Meteor.

Create a meteor project

```sh
meteor create meteor-tachyons
cd meteor-tachyons
```

Add postcss. This entails dropping meteors default css minifier, which works fine, but we want autoprefixer and inlined css imports and and all that good stuff. See: http://guide.meteor.com/build-tool.html#postcss for more info.

```sh
meteor remove standard-minifier-css
meteor add juliancwirko:postcss
```

```sh
npm install --save-dev postcss-easy-import autoprefixer
```

Add config to tell autoprefixer what browsers to add vendor prefixes for:

```json
  "postcss": {
    "plugins": {
      "postcss-easy-import": {},
      "autoprefixer": {
        "browsers": [
          "last 2 versions"
        ]
      }
    }
  }
  ```

  Install tachyons and import it from your `main.css`

  ```sh
  npm install --save tachyons
  ```

  ```css
  @import 'tachyons'
  ```

  And start using the [subatomic helpers] it offers in your html

  ```html
  <body class="sans-serif measure pa6">
    <h1 class="f-6">Welcome to Meteor!</h1>
    {{> hello}}
    {{> info}}
  </body>
  ```



---

[Tachyons CSS]: http://tachyons.io/
[subatomic helpers]: http://tachyons.io/docs/