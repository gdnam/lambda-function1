# Tạo S3 trigger lambda function thực hiện các thao tác lưu trữ trên DynamoDB.
# 1. Tạo S3 Bucket
# Nhập bucket name và nhấn Create bucket
## hình ảnh
![demo]()
# 2. Tạo Lambda Function
## hình ảnh
![demo]()
### Basic information
- Function name: codestar-t9-s3-trigger
- Runtime: Python 3.7
# Nhấn Create function
## hình ảnh
![demo]()
![demo]()
![demo]()
# Add thêm policy AmazonS3FullAccess và AmazonDynamoDBFullAccess vào Lambda Execution role
![demo]()
![demo]()
# 3. Code Lambda
# Cập nhật bucket name và nhấn Deploy
![demo]()
### Code 
 import json
 import boto3
 import random, string
 from boto3.dynamodb.conditions import Key, Attr

 def lambda_handler(event, context):


    bucketName = event['Records'][0]['s3']['bucket']['name']
    file_key = event['Records'][0]['s3']['object']['key']

    
    # Get the service resource.
    dynamodb = boto3.resource('dynamodb')
    
    # Change table name
    table = dynamodb.Table('test')

    
    chars=string.ascii_uppercase + string.digits
    randomId = ''.join(random.choice(chars) for _ in range(8))
    
    table.put_item(Item={
        'id': randomId,
        'file_key': file_key,
        'bucket': bucketName,
    })
    
    return {
        'statusCode': 200,
        'body': []
    }

### Optional: Test Lambda function
- Click Test
- Configure test event: s3-put
- Event name: s3-trigger-test
![demo]()
# Click Test nếu kết quả ra statusCode: 200 là đã cấu hình Lambda thành công
![demo]()
# 4. Add trigger cho S3 bucket
![]()
![]()
# 5. Quay trở lại S3 và upload 1 file lên
![]()
![]()
