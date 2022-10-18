# Tạo S3 trigger lambda function thực hiện các thao tác lưu trữ trên DynamoDB.
# 1. Tạo S3 Bucket
# Nhập bucket name và nhấn Create bucket
![demo](https://lh3.googleusercontent.com/9zQNdHqNrkPv-CvTbf2PbkZt6wv8RXzaN2kyVYsgOcY1SB2XrBIKrow55qnuzCZ0bVlW89NHRoV6a5QiNR8hOj98cipAcIfJgZ7EK_cpXGg7RbOjLJBXK1G_GQmaxy857fiaKO7l0Q=w2400)
# 2. Tạo Lambda Function
![demo](https://lh3.googleusercontent.com/ZQGntAx9fLmW-319DZHLtrtU8lhv72hUuCrTFIKvBhUjMkhAMsxRb18tGTPNbgcVpg30Mg7rm4YTPQcebGw6Ta7TUh4cwopEtQPpRVPbd0xbeV_hEEPH0Knmka-O3HjDflxVoi4EeA=w2400)
### Basic information
- Function name: codestar-t9-s3-trigger
- Runtime: Python 3.7
# Nhấn Create function
![demo](https://lh3.googleusercontent.com/VMhmIZLBGQbZ-Ek0jPlW6L2WFR4GrqZd09A7j9l8iw9hsE4oENfJu92oXw07fX8xvJOed4LGrcJSe8wBFJTEOzBicaeXFU3_VjicFn9uk6Jun8G3tg9O4ZC9M2mVRKM_eYoJ-eEyqw=w2400)
![demo](https://lh3.googleusercontent.com/BNAoljDpjnUEpdxsqtlitI_oettEv-siDCTzK2rt0AGz1R77WtfG2C-CuAEzA9iKR3AvoX5WOMBCARAbvddzX0a6XjQ3L1QlKJAto0jjJTviPj7Kh8kOa95_kLgblNjTzNmAjIXPXg=w2400)
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
'''
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
