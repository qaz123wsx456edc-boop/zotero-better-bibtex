{{/* DO NOT EDIT. This shortcode is created automatically from Preferences.xul */}}
### BibTeX

#### Export unicode as plain-text latex commands (recommended)

default: `yes`

BibTeX has really spotty Unicode support, so you generally want this on. It will translate things like accented characters
to their equivalent LaTeX constructs on export.

#### Disregard name prefixes when sorting

default: `no`

Name handling is a lot more complex than I had ever thought it to be. A *lot* more complex. BibTeX has
really limited ways of dealing with names with particles (van, von, de, etc). If you turn this on, BBT
will add code to have `van Gogh` sorted under `Gogh`.

#### Add URLs to BibTeX export

default: `no`

Most BibTeX styles do not support DOI/URL fields. Of the styles that do support them, many forget to load the required 'url' package, so make sure to load it yourself. DOI and URL fields are so-called 'verbatim' fields, and without the 'url' package loaded compilation will likely fail.

Options:

* no
* in a note field
* in a URL field

### BibLaTeX

#### Export unicode as plain-text latex commands

default: `no`

BibLaTeX actually has really good Unicode support, so you generally want this off. But for some geezers such as me it is
simply more pleasing to have things like accented characters translated to their equivalent LaTeX constructs on export.

#### Use BibLaTeX extended name format (requires biblatex 3.5)

default: `no`

Use the extended biber 2.7 format for names with particles - only works in BibLaTeX 3.5 or later.
This biblatex has a new (less ambiguous) way to store creator names. It's technically
superior, but the LaTeX world moves slowly, so many people won't have it yet. But if you're an early adopter,
you can enable it here

### Fields

#### When a reference has both a DOI and a URL, export

default: `both`

Does what it says on the tin, really. If a reference has both a DOI and an URL, you can choose to have them both exported, or either one of them. Note that for BibTeX,
you must load the `url` package when you have `doi` or `url` fields. `doi` and `url` fields are so-called `verbatim` fields with different escaping rules, and
BibTeX compilation will likely error out without the package loaded.

Options:

* both
* DOI
* URL

#### Fields to omit from export (comma-separated)

default: `<not set>`

If there are some fields you don't want in your bibtex files (such as `note` for example), add a list of them here, separated by comma's.

#### Include JabRef-specific metadata:

default: `no`

Export JabRef-specific fields: timestamps, and groups for each collection and item is part of. Note that format `4` will disable caching in exports, which is really undesirable specifically for auto-exports.

Options:

* no
* for JabRef 3
* for JabRef 4

### Miscellaneous

#### Automatically abbreviate journal title if none is set explicitly

default: `no`

If set, generates journal abbreviations on export using the Zotero journal abbreviator, according to the abbreviation style selected in the list below the checkbox.

#### Abbreviation style:

default: `<not set>`

Select the style for auto-abbreviation. Only applicable to Juris-M; in Zotero, the style for automatic
abbreviation is not configurable.

#### Include comments about potential problems with the references

default: `no`

Generate quality reports for exported references. These show up only in BibTeX and BibLaTeX report formats and indicate things like missing required fields and 
duplicate citation keys.

#### Include automatic tags in export

default: `yes`

Some importers or Zotero extensions (such as the ShortDOI manager for example) create tags on items that are more for item management than that
they are descriptive of the item. When this is off, such tags will not be included in the export.

#### When converting to plain-text latex commands:

default: `Minimize the number of switches between math-mode and text-mode`

When a unicode character can be exported as either a math-mode or text-mode command, map to:

* `minimal-packages`: if both a math-mode and a text-mode mapping is available, use the version that does not require
   extra packages to be loaded.
* `conservative`: if both a math-mode and a text-mode mapping is available, stay in the mode of the previously mapped
   character if possible. This minimizes the number of generated `$`s in the output.
* `text`: if both a math-mode and a text-mode mapping is available, prefer text.
* `math`: if both a math-mode and a text-mode mapping is available, prefer math.

Options:

* Minimize additional latex packages required
* Minimize the number of switches between math-mode and text-mode
* Prefer text-mode replacements
* Prefer math-mode replacements


