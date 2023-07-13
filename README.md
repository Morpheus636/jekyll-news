# jekyll-news
An all-in-one newspaper theme for Jekyll.

## Page Templates
### Home Page
To create the home page, make a file called `index.html` in the root directory and add the following text.
```yml
---
layout: home
permalink: /
title: Home
exclude: true
---
```

By default, any additional content in this file will go at the bottom of the page, just above the footer. If you would rather that this content be displayed in a sidebar, specify `is-sidebar: true` in the front matter. When the page size is too small to show a sidebar, it will be moved back to the footer.

### Normal Page
To create a basic page, make a .html or .md file anywhere in the repository and add the following front-matter:
```yml
layout: page
title:
nav-title: # OPTIONAL - specify a different title for the page when it appears in nav menus.
exclude: true # OPTIONAL - removes the page from the menu bar.
```

Then, add your content.

If you'd like to add a sidebar to this page, put your main content inside a `<div class="main-content">`, and the sidebar content directly below it in a `div class="sidebar"`.


### Articles
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
  alt-text: # Description of the image for accessibility reasons
layout: post
---
```

### Category Pages
To add a new category page, create a new HTML file in the root directory. Then add the following text:
```yaml
---
layout: category
title: # Here's where you put the name of the category this page is for.
permalink: # Here's where you put the relative path to this category page.
---
```

### Staff Profiles and Staff Directory
Create a staff directory page by creating a new HTML file with the following text:
```yaml
---
layout: staff-directory
title: Staff
permalink: /about/staff
---
```

Then, to add a staff profile, create a new markdown file in the `_staff/` directory and add the following text at the top:
```yaml
---
layout: staff-profile
title: # Here's where you put the name of the staffer
author-title: # Here's where you put the staffer's title
mug-path: # Here's where you put the URL of the staffer's mugshot
---
```
After that, write their bio.

## Configuration
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
```

### Google Analytics
To enable Google Analytics, add your measurement ID in `_config.yml` as follows:
```yaml
google_analytics: # Here's where your measurement ID goes.
```

### AdSense
> **Note**
> These instructions rely on you having control of and serving this site from a apex domain, not a subdomain

1. Create an AdSense account at https://adsense.google.com/adsense/signup
2. On the "A couple things before you start" page, select "I don't have a site yet", opt in or out of notifications, enter your country, then agree to the TOS.
3. On the "Lets get you started" page, click "Add site" and enter your apex domain.
4. Click "Let's go" under "Connect your site to AdSense"
5. Copy the Client ID from the code snippet.
  - This is the part right after `?client=` (everything from the `=` to the `"`).
  - It should be in the format `ca-pub-xxxxxxxxxxxxxxxx` (the exact number of digits might vary)
6. In _config.yml, add the following code:
```yaml
adsense:
  enabled: true
  client: # Put the Client ID you just copied here
```
7. Deploy your changes.
8. Back on the AdSense page with the code snippet, check the box that says "I've placed the code" and click Next, and then Request review.
9. Enter your payment information on the AdSense dashboard.
10. Start placing ads. Simply add `{%- include adsense.html -%}` anywhere you want an ad to appear.

> **Warning**
> Ensure you comply with privacy regulations like [GDPR](https://support.google.com/adsense/answer/7670013?hl=en) and [CCPA](https://support.google.com/adsense/answer/9560818?hl=en) before showing ads to your users.

## Overriding Style
Create a file called `_sass/overrides.scss`. Any styles in it will override existing styles. 

## Custom Head
Create a file called `_includes/head-custom.html`. It's contents will be added at the end of the template's `<head>`.