# jekyll-news
A simple newspaper theme for Jekyll.

## Creating Articles
To add a new article, create a markdown file in `_posts/` with the following name format: `YYYY-MM-DD-SLUG.md`.

Then, at the beginning of the file, add the following front-matter.  Not all of this is required, but things may not look right if you don't include everything.

```yml
---
title: # Headline
subhed: # Subhead
author: # Reporter Name
author-title: # Reporter Title
featured-image: 
  path: # URL or relative path to the post's featured image
  cutline: # Caption for the image
  credit: # Photo credit for the image
layout: article
---
```

## Configuration and Customization
### Author
The `author` value in `_config.yml` is used for the copyright notice in the site footer.
### Title
The `title` value in `_config.yml` is the name of the site.
### Description
The `description` value in `_config.yml` is the text that appears next to the coopyright notice in the site footer.

### Flag:
To modify the flag, add the following to `_config.yml`:
```yaml
flag:
  show: true
  path: # Here's where you put the URL (or relative path) to your flag image
```
Alternatively, you can completely override the default flag by creating a new `_includes/flag.html`

### Disqus:
To enable Disqus comments on posts, add the following to `_config.yml`:
```yaml
disqus:
  enabled: true
  shortname:  # Here's where you put your unique shortname
```Lead Developer