# s3-static-website
This is a project to demonstrate static website hosting in S3. In this project we will store our html contents in s3 and we will not publicily expose the s3 bucket. We will create a cloud front distribution and allow cloud front to consider S3 as its origin . S3 will have a policy to only allow get requests from cloudfront, in that way it secures itself from other direct accesses.
We will register a domain in any of the registar and perform a CNAME mapping with our cloudfront distribution url.
We will also create a ACM ssl certficate and map it to our domain.
