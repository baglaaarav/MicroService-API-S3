## MicroService that add data to S3 bucket through API gatway

#### A microservice adds data to an S3 bucket through an API Gateway, with a Kinesis Data Stream and Kinesis Data Firehose situated between the S3 bucket and the API Gateway.

#### Resources used in this project:
- API Gateway
- Kinesis Data Stream
- Kinesis Data Firehorse
- Postman
- S3


### Project Architecture:
https://github.com/baglaaarav/MicroService-API-S3/blob/main/diagram.png

### What I did:
Firstly, I initiated the process by creating an IAM user with specific permissions. Subsequently, a Kinesis data stream named "test" was crafted with Capacity mode configured as on-demand. Following this, a role and policy were devised for API Gateway to assume, thereby granting the role the capability to insert data into one of the shards.

In the subsequent steps, an API Gateway was established, featuring a POST method and a designated resource directing data to the Kinesis destination. To ensure functionality, a test was conducted within the API Gateway, involving the direct posting of data into the Kinesis stream.

Upon successful testing, the API was deployed, and the resulting URL was acquired for use in Postman. Raw data was then posted through Postman, making it visible in one of the shards within the Kinesis Data Stream.

In continuation, an S3 bucket was created, configured to exclusively permit traffic routed through Kinesis Data Firehose. Following this setup, a Kinesis Data Firehose was created to channel data into the S3 bucket, creating a seamless flow that makes the data accessible within the Kinesis Data Stream.

In conclusion, the outlined steps constitute the establishment of a microservice architecture. This microservice efficiently adds data to an S3 bucket through a well-orchestrated API Gateway, Kinesis Data Stream, and Kinesis Data Firehose integration. By carefully configuring IAM user permissions, Kinesis settings, and S3 bucket access, this microservice ensures a streamlined flow of data from API input to its ultimate storage destination in S3. This robust architecture underscores the seamless integration of AWS services to create a reliable and scalable solution for data processing and storage.s