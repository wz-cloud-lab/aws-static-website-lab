# AWS Static Website Lab

This repository documents a hands-on AWS lab for hosting a static website using Amazon S3 and Amazon CloudFront.

The goal of this lab is to practice basic cloud infrastructure concepts, including static asset hosting, CDN delivery, private S3 bucket access, and CloudFront cache invalidation.

## Live Demo

The website is available via CloudFront:

https://d3nyo2knndb3j8.cloudfront.net

## Project Overview

This project deploys a simple static website for an international student guide. The website content is hosted in a private Amazon S3 bucket and delivered through Amazon CloudFront.

The S3 bucket is not publicly accessible. CloudFront is configured to access the bucket securely through Origin Access Control.

## Architecture

```text
User Browser
    ↓ HTTPS
Amazon CloudFront
    ↓ Origin Access Control
Private Amazon S3 Bucket
    ↓
index.html / style.css
