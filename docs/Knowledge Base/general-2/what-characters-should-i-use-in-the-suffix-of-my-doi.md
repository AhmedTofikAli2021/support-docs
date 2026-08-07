---
title: What characters should I use in the suffix of my DOI?
excerpt: ''
deprecated: false
hidden: true
link:
  new_tab: false
  url: https://support.datacite.org/docs/doi-basics#suffix
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The easiest and recommended option is to use a randomly generated suffix. We group the suffix into blocks of 4, separated by a hyphen. You can generate a random suffix in both Fabrica and the API.

> 👍 Auto-generate a suffix
> 
> The auto-generate DOI name functionality means the DOI suffix is generated automatically and will look something like this: `10.15138/33bv-s284`

If you choose not to use this option, remember:

1. The DOI suffix must be unique within each prefix. The optimum length of a DOI suffix is 6–10 characters. 

2. Only use `a-z`, `0-9` and `-` in a DOI suffix. Other characters might have special meaning or will be escaped. DOI suffixes are [not case sensitive](https://support.datacite.org/docs/datacite-doi-display-guidelines#dois-urls-and-case-sensitivity).

3. Avoid human-readable information in a DOI suffix because any meaning may change over time. Further advice on [DOI suffixes](https://support.datacite.org/docs/doi-basics#suffix).

> 🚧 Reserved Characters
> 
> Reserved characters should not be included in a DOI suffix:  
> `;` \| `/` \| `?` \| `:` \| `@` \| `&` \| `=` \| `+` \| `$` \| `,`

## More information

[Suffixes documentation](doc:doi-basics#suffix)