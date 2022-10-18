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
![demo](https://lh3.googleusercontent.com/AcIKMJz_ifgdkvbUCA57ynHpuiUxtv1mulAxCQr1UjnBmZL6QE1WEpUCcexPqkffdn-BC2XGtGLFnjhOuagZlAwNVjjiKHqgHb83TEoI-zYAiVI6JvQgJZ1a6ZcY7e3WaLdUNmcYwQ=w2400)
# Add thêm policy AmazonS3FullAccess và AmazonDynamoDBFullAccess vào Lambda Execution role
![demo](https://lh3.googleusercontent.com/Q3PsJe0Gmx4I7Tze76oJ5zmcuGclZjZIFTtfvuZZCHQaRoGNHqL-3fjbiq5IC1qwvDSDpY0qUL9wUEKtBCUjQ0XCBj9F0q5UCyU0ylJQhxwPw0FUq0gT9AvWqtMq-MIygKYIsQ7X1g=w2400)
![demo](https://lh3.googleusercontent.com/maRIsD7WQXViL55sgIx4sA0mWsV2jdI6i6S-xRwWSWMMUzA3PZO9Ugy_t8sxHVreRsLaY3sjDNUZY2dzdB29z2dt67c12pqkW4ypNzWPQEEPYe8ewgMspZfXRqnBTRJhnFIzV5BZQQ=w2400)
# 3. Code Lambda
# Cập nhật bucket name và nhấn Deploy
![demo](https://lh3.googleusercontent.com/PR1-vkKObgq4bc4TfwWoGS891andYxWZWYqaD5mgYs2AcqcuoxoQ_npGn49aTdLdOZAHxy1h1sOZVRLQT865unuBHy1tsAZXW5AEKEa9fsyBeUH-FbUTZNijOau4lonbZVvLrtU93Q=w2400)
# Code 
![demo](https://lh3.googleusercontent.com/rF5-4lpzKUedL_sH6q87HJhSBhVcPDiJZXAqZ53qQTNKLILhpKraUDsKUWOu1Tn8qaJusdRaox6riowNN0SVyan1Fst5b2MspL0XU9FYq6WWqjaj599U-GI9KUdvYwc-3kiQs50elQ=w2400)
### Optional: Test Lambda function
- Click Test
- Configure test event: s3-put
- Event name: s3-trigger-test
![demo]()
# Click Test nếu kết quả ra statusCode: 200 là đã cấu hình Lambda thành công
![demo]()
# 4. Add trigger cho S3 bucket
![demo]()
![demo]()
# 5. Quay trở lại S3 và upload 1 file lên
![demo]()
![demo]()
