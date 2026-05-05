# AWS Static Website Lab

This repository documents a hands-on AWS lab for hosting a static website using Amazon S3 and Amazon CloudFront.

The goal of this lab is to practice basic cloud infrastructure concepts, including static asset hosting, CDN delivery, private S3 bucket access, and CloudFront cache invalidation.

## Live Demo

The website is available via CloudFront:

https://d3nyo2knndb3j8.cloudfront.net

## Project Overview

This project deploys a simple static website for an international student guide. The website content is hosted in a private Amazon S3 bucket and delivered through Amazon CloudFront.

The S3 bucket is not publicly accessible. CloudFront is configured to access the bucket securely through Origin Access Control.

## Security Design

- S3 bucket is configured with Block Public Access enabled
- No public access to S3 objects via direct URL
- CloudFront is the only entry point to access content
- Origin Access Control (OAC) is used to securely connect CloudFront to S3
- Bucket policy restricts access to a specific CloudFront distribution

This ensures that content is not directly exposed through S3 and must be accessed through the CDN layer.

## Architecture

```text
User (Browser)
    ↓ HTTPS
Amazon CloudFront (CDN)
    ↓ Origin Access Control (OAC)
Amazon S3 (Private Bucket)
    ↓
Static Website Files (HTML, CSS)
