# S3

* Object storage
* Supports versioing
* S3 durability is 99.999999999% (11)
* s3 availability is 99.99%
* Transfer accelaration through cloud front
* Supports replication (inter region and intra region) but storage cost is doubled. The SLA for replication is not great about 15 minutes for 99%
* S3 consistency model detailed below
* S3 can publish events to SQS, SNS, Lambda for replication, creation, deletion, restorating, lost in Reduced Reduncency storage

## Scenario 1 Atomic
* PUT /key-prefix/cool-file.jpg 200
* GET /key-prefix/cool-file.jpg 200

## Scenario 2 Eventual
* GET /key-prefix/cool-file.jpg 404
* PUT /key-prefix/cool-file.jpg 200
* GET /key-prefix/cool-file.jpg 404

## Scenario 3 Eventual
* PUT /key-prefix/cool-file.jpg 200
* PUT /key-prefix/cool-file.jpg 200 (new content)
* GET /key-prefix/cool-file.jpg 200
