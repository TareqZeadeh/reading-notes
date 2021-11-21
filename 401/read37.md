# S3

## [Introduction to Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html)

### What is Amazon S3?

Amazon Simple Storage Service (Amazon S3) is storage for the Internet. It is designed to make web-scale computing easier.

### Advantages of using Amazon S3

1. Creating buckets – Create and name a bucket that stores data. Buckets are the fundamental containers in Amazon S3 for data storage.

1. Storing data – Store an infinite amount of data in a bucket. Each object is stored and retrieved using a unique developer-assigned key.

1. Downloading data – Download your data or enable others to do so. Download your data anytime you like, or allow others to do the same.

1. Permissions – Grant or deny access to others who want to upload or download data into your Amazon S3 bucket. Grant upload and download permissions to three types of users. Authentication mechanisms can help keep data secure from unauthorized access.

1. Standard interfaces – Use standards-based REST and SOAP interfaces designed to work with any internet-development toolkit.

### Amazon S3 concepts

1. Buckets
   - A bucket is a container for objects stored in Amazon S3. Every object is contained in a bucket.
1. Objects
   - Objects are the fundamental entities stored in Amazon S3. Objects consist of object data and metadata. The data portion is opaque to Amazon S3. The metadata is a set of name-value pairs that describe the object.
1. Keys
   - A key is the unique identifier for an object within a bucket. Every object in a bucket has exactly one key.
1. Regions
   - You can choose the geographical AWS Region where Amazon S3 will store the buckets that you create.

### Amazon S3 data consistency model

1. Amazon S3 achieves high availability by replicating data across multiple servers within AWS data centers. If a PUT request is successful, your data is safely stored. Any read (GET or LIST) that is initiated following the receipt of a successful PUT response will return the data written by the PUT.

1. Bucket configurations have an eventual consistency model. Specifically:

   - If you delete a bucket and immediately list all buckets, the deleted bucket might still appear in the list.

   - If you enable versioning on a bucket for the first time, it might take a short amount of time for the change to be fully propagated.

### Amazon S3 features

1. Storage classes
   - Amazon S3 offers a range of storage classes designed for different use cases.
1. Bucket policies
   - Bucket policies provide centralized access control to buckets and objects based on a variety of conditions, including Amazon S3 operations, requesters, resources, and aspects of the request (for example, IP address).

### AWS Identity and Access Management

You can use AWS Identity and Access Management (IAM) to manage access to your Amazon S3 resources.

### Access control lists

You can control access to each of your buckets and objects using an access control list (ACL).

### Versioning

You can use versioning to keep multiple versions of an object in the same bucket.

### Operations

Common operations

1. Create a bucket
1. Write an object
1. Read an object
1. Delete an object
1. List keys

### Amazon S3 application programming interfaces (API)

The Amazon S3 architecture is designed to be programming language-neutral, using AWS Supported interfaces to store and retrieve objects.

### The REST interface

The REST API is an HTTP interface to Amazon S3. Using REST, you use standard HTTP requests to create, fetch, and delete buckets and objects.

### The SOAP interface

The SOAP API provides a SOAP 1.1 interface using document literal encoding. The most common way to use SOAP is to download the WSDL, use a SOAP toolkit such as Apache Axis or Microsoft .NET to create bindings, and then write code that uses the bindings to call Amazon S3.

## [S3 with Amplify](https://docs.amplify.aws/lib/storage/getting-started/q/platform/android/)

1. To start provisioning storage resources in the backend, go to your project directory and execute the command: `amplify add storage`
1. `amplify push`

### Install Amplify Libraries

`implementation 'com.amplifyframework:aws-storage-s3:1.24.0' implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'`

### Initialize Amplify Storage

```java
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSS3StoragePlugin());
```

### Uploading data to your bucket

To upload to S3 from a data object, specify the key and the data object to be uploaded.

1. Upon successfully executing this code, you should see a new folder in your bucket, called `public`. It should contain a file called `ExampleKey`, whose contents is `Example file contents`.