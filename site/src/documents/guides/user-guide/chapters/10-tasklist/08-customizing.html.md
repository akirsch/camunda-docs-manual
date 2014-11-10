---

title: 'Customizing'
category: 'Tasklist'

---

You can override the default configuration of the tasklist using a central configuration file
located in `app/tasklist/scripts/config.js`. Currently, the following configuration options are
available:

##Date Format

Dates can be configured by specifying a `dateFormat` object. The values of the properties of this
object must be strings representing date formats in accordance to
[moment.js](http://momentjs.com). Following date formats are used within the tasklist:

- `monthName` represents the name of a month (e.g. January).
- `day` represents the number of a day in a month (1..31).
- `abbr` represents a short format of a date including time.
- `normal` represents the standard format of a date including time.
- `long` represents a verbose format of a date including time and day of the week.
- `short` represents a short format of a date excluding time.


###Example

```javascript
"dateFormat": {
  "monthName": "MMM",
  "long":   "LLLL"
}
```

## Localization

The localization of the tasklist is contained in the `app/tasklist/locales/` directory. This
directory contains a separate localization file for every available language. The file name
consists of the language code and the suffix `.json` (e.g. `en.json`).

To change the language the tasklist operates with, you can set the `preferredLocale` property in
the configuration file:

```javascript
"locales": {
  "preferredLocale": "en"
}
```

The language code specified in the configuration file must match the language code of one of the
locale files in the `locales` directory.

To create a new localization for the tasklist, copy the provided language file, translate it and
save it as new localization file with the corresponding language code. You can then use the
custom localization by setting `preferredLocale` in the configuration file to the new language.

## Logo and Header Color

To change visual aspects of the tasklist you can edit the user stylesheet file located in
`app/tasklist/styles/user-styles.css`. This file contains CSS which is loaded into the tasklist
and can override the standard styles.

To display your own logo in the top-left corner, edit the `background-image` property of the
`.navbar-brand` to point to the URL of your logo image.

To set the color of the navigation bar (header), multiple properties have to be overwritten. You
can find an example in the default `user-styles.css` file.

In addition to the basic `user-styles.css` file, you can edit the source style- and layout files
using [less](http://lesscss.org/) to change the overall appearance of the tasklist.