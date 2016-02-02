Backups in S3 and Glacier

Tags: backups, s3, glacier, storage, s3-ia

# Three ways to store files in Amazon

Standard storage, Infrequent Access Storage and Glacier.
Differ on availability, durability, price for storage and price for retrieval

FIXME a table
  * Standard
    * Availability SLA: 99%
        Durability: 11 9s

    Standard - IA
    Glacier

| Method  | Availability SLA | Durability 9s | Storage price | Retrieval price |
|---------|------------------|---------------|---------------|-----------------|
| S3      | 99%              | 11            |               |                 |
| S3-IA   |   |   |   |   |
| Glacier |   |   |   |   |
    
Encrypted buckets FIXME Server-Side Encryption with Customer-Provided Encryption Keys (SSE-C) where they claim not to store the key, and to use some HMAC salted version of the key
FIXME EBS volumes
FIXME Reduced Redundancy Storage

# Lifecycle policies
Some policies can be defined for S3 buckets, like to *promote* a file to Glacier or to S3-IA after 10 or 30 days. Or just to remove it. See [2].

# Conclussions
costs? FIXME glacier is like 4 times lower than s3.
Cost comparinson, internal file: https://hipchat.zalando.net/files/1/1416/e1SZtfQYcULrK6o/Bildschirmfoto%202015-10-06%20um%2013.40.23.png

# Abbr

  * IA: Infrequent Access
  * SLA: service level agreement

# Refs
1. [AWS Offers New S3 Standard – IA Storage Class for Rarely Used Files](http://www.cloudwards.net/news/aws-offers-new-s3-standard-ia-storage-class-for-rarely-used-files-9775/)
2. [Moving old backups from s3 to Glacier](https://aws.amazon.com/blogs/aws/archive-s3-to-glacier/)
3. [Amazon FAQs - ](http://aws.amazon.com/s3/faqs/#amazon-glacier_anchor)
4. [Getting started with AWS Glacier](https://docs.aws.amazon.com/amazonglacier/latest/dev/getting-started-create-vault.html)
5. [Protecting Data Using Server-Side Encryption](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html)