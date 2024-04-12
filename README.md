# s3-static-website
This is a project to demonstrate static website hosting in S3. In this project we will store our html contents in s3 and we will not publicily expose the s3 bucket. We will create a cloud front distribution and allow cloud front to consider S3 as its origin . S3 will have a policy to only allow get requests from cloudfront, in that way it secures itself from other direct accesses.
We will register a domain in any of the registar and perform a CNAME mapping with our cloudfront distribution url.
We will also create a ACM ssl certficate and map it to our domain.

#Steps

1. Create a S3 bucket with the name of your domain (www.techsystemdesign.com). Don't allow public access. So that files can not be directly accessed.
2. Upload your index.html and other static contents.
3. Create a cloudfront distribution. Previously created bucket will be its origin.
4. Redirect http to https. Provide alternate domain name same as original (www.techsystemdesign.com)
5. Under origin access section, select Legacy access identities . Create a origin access identity. Select update bucket policy. This will update bucket policy to allow access from the cloudfront principal.
6. Enable security protection.
7. Choose a custom certficate. Create a certificate using AWS certification manager.
8. Map the cname records in your ddomain provider (godaddy) to validate. Once certificate issued use it on cloudfront.
9. Now you can access using your cloudfront distribution url.
10. Create another cname record with your domain provider like Route 53 or godaddy and map your domain with the cloudfront distribution url.
