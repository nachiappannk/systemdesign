# S3

* Object storage
* Supports versioing
* S3 durability is 99.999999999% (11)
* s3 availability is 99.99%
* Transfer accelaration through cloud front
* Supports replication (inter region and intra region) but storage cost is doubled
* S3 consistency model

Atomic
PUT /key-prefix/cool-file.jpg 200
GET /key-prefix/cool-file.jpg 200

Eventual
GET /key-prefix/cool-file.jpg 404
PUT /key-prefix/cool-file.jpg 200
GET /key-prefix/cool-file.jpg 404

Eventual
PUT /key-prefix/cool-file.jpg 200
PUT /key-prefix/cool-file.jpg 200 (new content)
GET /key-prefix/cool-file.jpg 200
