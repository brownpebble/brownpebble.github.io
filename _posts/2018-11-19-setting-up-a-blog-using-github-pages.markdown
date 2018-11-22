---
layout: post
title:  "Setting Up A Blog Using GitHub Pages"
date:   2018-11-19 23:04 -0600
categories: blog jekyll github
---
# Introduction

You can set up a blog using GitHub Pages. GitHub Pages uses Jekyll as a blog
platform. Jekyll is flexible and suitable for a programming blog.

# Creating a git repository in GitHub for a blog site

# Setting up a jekyll

# Creating a blog site skeleton

# Using a custom domain with GitHub Pages

Two types of domains are supported by GitHub Pages: _apex domains_ and
_subdomains_.

- An _apex domain_ is a custom domain without a subdomain part, such as
  `example.com`.
- Whereas, a _subdomain_ has a subdomain part, such as `blog.example.com`.

GitHub strongly recommends using **www subomain**, such as `www.example.com` for
these reasons. _From [help.github.com][github-help-wwwsubdomain]_

- It gives your GitHub Pages site the benefit of our Content Delivery Network
- It is more stable because it is not affected by changes to the IP addresses of
  GitHub's servers.
- Pages will load significantly faster because Denial of Service attack
  protection can be implemented more efficiently.

## Configuring a `CNAME` record with your DNS provider

If you decide to use `www.brownpebble.com`, you need to add a CNAME DNS record that
redirects the web browsers to `brownpebble.github.io`. How to
configure a CNAME record depends on the DNS provider but it would usually look
like the below.

```
www	CNAME	1h	brownpebble.github.io
```

To verify if the DNS record works as intended, use the dig command.

```
$ dig www.brownpebbles.com +nostats +nocomments +nocmd
;www.brownpebble.com.		IN	A
www.brownpebbles.com.	3599	IN	CNAME	brownpebble.github.io.
brownpebble.github.io.	3598	IN	A	185.199.109.153
```

The GitHub domain that `www` needs to be redirected to varies based on the type
of the GitHub Pages site. Refer to the GitHub help page, [Custom domain
redirects for GitHub Pages sites][github-help-custom-domain-redirects]

## Adding a custom domain for your GitHub Pages site

Now you need to add your custom domain `www.brownpebble.com` to your GitHub
Pages site. You can find the setting on **Settings** page on your GitHub Sites
repository. Go to **Settings** -> **Options** and look for "Custom Domain" in
"GitHub Pages" section on the page.

[github-help-wwwsubdomain]: https://help.github.com/articles/about-supported-custom-domains/#www-subdomains
[github-help-custom-domain-redirects]: https://help.github.com/articles/custom-domain-redirects-for-github-pages-sites/
