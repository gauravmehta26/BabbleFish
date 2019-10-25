# BabbleFish
So you can understand all languages of the world

### Setup Babel Fish
- Create S3 bucket in your account
- Copy following folders in your bucket
    1. cloudformation
    2. css
    3. images
- Copy following files in your bucket
  1. voice-translator.html
  2. voice-translator.js
  3. voice-translator-config.js
  4. babel-fish-app-1.0.jar (build file to lambda)
  
- Execute cloudformation template from s3 bucket copied in last step
````
aws cloudformation create-stack --stack-name babel-fish-stack  \
    --template-body https://<bucketname>.s3-<region>.amazonaws.com/cloudformation/babblefish.yaml \
    --parameters ParameterKey=BucketName,ParameterValue=<bucketname> \
    --region eu-west-1 \
    --capabilities CAPABILITY_IAM \
    --tags Key='Block ID','Value=BLK0001220' Key='OAR/OPR ID',Value='AAB.SYS.SANDBOX'    
````

