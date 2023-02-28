CI CD + AWS Deploy: /
  1: Create AIM user with full s3 and beanstalk Permissions /
  2: Create Access Key and Create Secret Key in AIM user /
  2: Create s3 bucket / 
  3: Create beanstalk with python in AWS /
  4: Create Secrets access_key and secret_key in Settings on github /
  
  global environment: /
    EB_PACKAGE_S3_BUCKET_NAME : "your s3 bucket name" /
    EB_APPLICATION_NAME       : "MyFlask" /
    EB_ENVIRONMENT_NAME       : "MyFlask-env"/
    DEPLOY_PACKAGE_NAME       : "flask_app_${{ github.sha }}.zip" /
    AWS_REGION_NAME           : "eu-north-1"   #your region aws /

  connect to AWS: /
    aws-access-key-id     : ${{ secrets.MY_AWS_ACCESS_KEY }} /
    aws-secret-access-key : ${{ secrets.MY_AWS_SECRET_KEY }} / 
    aws-region            : ${{ env.AWS_REGION_NAME}} /

  


[![CI-CD-Pipeline-to-AWS-ElasticBeanstalk](https://github.com/oleksiifutruk/ci_cd/actions/workflows/main.yml/badge.svg)](https://github.com/oleksiifutruk/ci_cd/actions/workflows/main.yml)
