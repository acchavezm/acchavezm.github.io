---
layout: page
title: New template
permalink: /aws-dataengineering-day/template
parent: Data Engineering Immersion Day
nav_order: 3
---

# Revised template
Here's the WIP

```yaml
Resources:
  RawS3Bucket:
    Type: AWS::S3::Bucket
  ProcessedS3Bucket:
    Type: AWS::S3::Bucket
  FirehoseDeliveryStream:
    Type: AWS::KinesisFirehose::DeliveryStream
    Properties:
      S3DestinationConfiguration:
        BucketARN: !Sub arn:aws:s3:::${RawS3Bucket}
        BufferingHints:
          IntervalInSeconds: 60
          SizeInMBs: 50
        CompressionFormat: GZIP
        Prefix: weblogs/raw/
        RoleARN: !GetAtt S3Role.Arn
```