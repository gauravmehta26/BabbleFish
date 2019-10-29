# BabbleFish
So you can understand all languages of the world

### Setup Babel Fish
- Create S3 bucket in your account
- Copy following folders in your bucket
    1. babel-fish-app-1.0.jar (build file to lambda)
    2. cloudformation

- Execute cloudformation template from s3 bucket copied in last step
````
aws cloudformation create-stack --stack-name babel-fish-stack  \
    --template-body https://<bucketname>.s3-<region>.amazonaws.com/cloudformation/babblefish.yaml \
    --parameters ParameterKey=BucketName,ParameterValue=<bucketname> \
    --region eu-west-1 \
    --capabilities CAPABILITY_IAM \
````

- Edit voice-translator-config.js with the values from output of cloudformation stack 
- Copy following folders to bucket created by cloudformation stack
    1. css
    2. images
- Copy following files to bucket created by cloudformation stack
  1. voice-translator.html
  2. voice-translator.js
  3. voice-translator-config.js
  

- Copy the endpoint url from the output of cloudformation stack and open it in browser
  