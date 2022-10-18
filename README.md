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
![demo](https://lh3.googleusercontent.com/EzeWUI2s9MtF1doJtDbHqiC_GWgiTW0TkeyIxSKV3MtiN-HipDVlBlEMvzLzj1dbngNWR0_KNARSkvbcjy7hfEwvrq-ZvxDhJ7pLYcuKRxrw-nMP64a6wK7OK4W3CssEvfHkeEPbDg=w2400)
# Click Test nếu kết quả ra statusCode: 200 là đã cấu hình Lambda thành công
![demo](https://lh3.googleusercontent.com/sEuBulTH6UStqD8MbN1nBgrsZV2hun95YBqi1zQaBTVGdToF1bqL2LzCE1csKyj8NEYh59B0hhS7BG0dfHh8cupnS1P_mMYiapOS65jNOAfZXW6oVeRxRc9Siq0HV5wPgz_ZdAFwGw=w2400)
# 4. Add trigger cho S3 bucket
![demo](https://lh3.googleusercontent.com/SNNXwaLwHhQswUpT1mHXBGeWvEZ3I_MG-G9d-aIQ2J6ZEuHc9GXs4-qxwJK5Ce25-PjXj9KPddjKJTh5F1sboeS9qc3IBr2Tm_iVCn86TMMNDbfwT4zAtvcamT58Xp6SImleLzjPMw=w2400)
![demo](https://lh3.googleusercontent.com/PJDwboIq4VgC49n6eXpnE_ZgLsG1UVrCWpKb_kRWp_6S17pbp6SbuFBKr40VJcYFPHM189HZ1eBjg78CIAf8hbX11P_7PGcKn8zhiyE7sHvy9GIuPlJ_hQnKSndv2wXzoIQ40NFQtQ=w2400)
# 5. Quay trở lại S3 và upload 1 file lên
![demo](https://lh3.googleusercontent.com/yW_MiQ_3OAu2JzV1Qmorm1mT_X8ctAHHiC6-8mijTLVeHQJBK9lpKFZMDhfheZ2CDQPo91lIs6E6ivm78cX4pQZT2Fku28n4tJrYBryIKZOI-2bwJ83HsKQlk0PfzsW8Al648CMYyA=w2400)
![demo](https://lh3.googleusercontent.com/9EMvfgfeKbastxPf35EuALXE-haFxWRiZ7Jx6iWdgV4wgx6mIAsoItLNpUKwtFwfzZGNkeglfnV8xW9k8VN3vgzxt4uYqcClcQvtIU474eJBkCYhbNw4DXkgZrmMSsDUxDeEtGaR0w=w2400)
