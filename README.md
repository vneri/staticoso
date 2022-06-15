# staticoso

Just {{ replace }} any variable in your html, js, css files with values or includes.
Support for languages or other kinds of selectors is automatic.

Usage:

Use the placeholder variables in your source file:

```html
  <html>
    <head>
      <title>{{ title }}</title>
    </head>
    <body>
      <nav>{{ navigation }}</nav>
      <h1>{{ header }}</h1>
    </body>
  </html>
```

Add the definition to the staticoso.json of your project

```json
{
    "variables": {
        "title": "My website",
        "header": {
            "en": "Welcome to my website!",
            "de": "Willkommen zu meiner Webseite!",
            "it": "Benvenuti sul mio sito!"
        }
    },
    "includes": {
        "navigation": {
            "en": "navigation_en.html",
            "de": "navigation_de.html",
            "it": "navigation_it.html"
        }
    },
    "settings": {
        "extensions": [
            "html",
            "htm",
            "css",
            "js"
        ]
    }
}
```

Note how you can add the language selector or simply omit it, if you have a variable content that is always standard.
Same applies to the includes.

The standard output folder is /public, as a subfolder of the source folder. The created files will automatically have the selector in the filename.
So, if you choose to create the German version of a site, the result will be: index_de.html

You call the script like this:

```
node staticoso.js /sourceFolder (selector|optional)
