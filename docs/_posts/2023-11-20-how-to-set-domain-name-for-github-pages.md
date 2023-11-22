---
title: How to set your domain name via GoDaddy for GitHub Pages
tags: [Domain name , GitHub Pages]
style: fill
color: success
description: A note for setting domain name via GoDaddy for GitHub Pages
---
Source: [GitHub Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site)

Assume that you already have your domain name with GoDaddy.
All you need to do is to set your domain correctly and the follows are the key parts:

1. Within the DNS section, point your custom domain to GitHub’s server over HTTPS
2. add CNAME with www for your GitHub Pages
3. set the other servers

so your DNS records will at least include following items:

|Type|Name|Value|TTL|
|----|----|----|----|
|A|@|185.199.110.153|600 seconds|
|CNAME|www|\<repo name>.github.io|1 hour|
|A|@|185.199.109.153|1 hour|
|A|@|185.199.111.153|1 hour|
|A|@|185.199.108.153|1 hour|

After that, ensure to add a new file named "CNAME" in your repository and only put your domain name as its content.
Once you push all changes to GitHub, make sure you also enforce HTTPS in your repo setting (Settings>Pages>Custom domain), and you are all set.

