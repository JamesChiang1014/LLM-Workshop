# LLM-Workshop instruction guide
## Environments preparation
Login Event Environments
+ Enter Your hashkey for login
  <img width="1397" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/2695f568-d13d-46e1-937f-2150d1061e0b">
+ Enter your email and get one time password for login
+ Select AWS console for access console environments
  <img width="1112" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/d188f5b1-682b-4ff4-b08e-d822c662be8e">
+ Select Open Console
  ![image](https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/84a19fab-a3ed-4ebb-a634-f46634a67098)
+ Login Success
  <img width="1265" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/29d322ea-029c-440c-90fb-da0b9b8daab6">

## LLM Workshop Deployment
Step 1. Create IAM users
+ Search IAM and create a user
  ![image](https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/67f76593-fd90-4682-8ec4-455cf1cd2270)
+ Provide a user name, ex:LLM_Deployment
  <img width="1009" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/5c5a8fd7-78b3-4a80-8dda-df19c89bcad2">
+ Attached Admin policy to this user and create user
  ![image](https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/4fe1ab1c-91ad-4541-9605-27b78ef654c0)
+ Select this user again and click secuiry credentails
  ![image](https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/e8a6802e-54b7-4b52-bffd-b2ca9628c6f7)
+ Find the access key and create access key
  ![image](https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/d5283a2e-f238-48a6-8a4a-8988dca8a1b6)
+ Select CLI an confirm the reminder, next. Create the access key
  <img width="779" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/91986e5f-3b5b-4033-81a7-e389e4e72dfe">
+ Copy Access key and Secret access key to local text file
  ![image](https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/0e720b37-928d-459f-8f98-0941860c312b)
Step 2. Create cloud9 instance
+ Create cloud9 environments
<img width="1379" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/4790aa42-f26a-40c6-bb1c-2d165bcec8bb">

+ Provide a name, select t3.small instance, create
  <img width="1090" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/48b975dd-f987-4199-8c5a-761cc6dd3d17">
  
+ After instance created, open in Cloud9
  <img width="1095" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/17faec45-623f-400d-8cc6-93b1916dd32c">
  
+  use **aws configure** and enter the Access key and Secret access key you just record before. leave the region by default
  <img width="776" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/a414be62-3ddf-465f-a720-375cb90af7f0">
  
+ select force update
  
  <img width="507" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/028969bc-7899-45f8-972d-f25316dd755f">
+ Download workshop package to cloud9 instance
  ```javascript
  wget https://jameschiang1001.s3.amazonaws.com/smart_search-v2-k.zip
  ```
  <img width="1145" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/474bb175-21b4-4d49-821d-e6d1654c6807">
+ unzip the download file
  ```javascript
  unzip smart_search-v2-k.zip
  ```
Step 3. Deploy LLM+Kendra workshop package
+ use cdk to deploy lambda, kendra and sagemaker service
  ```javascript
  cd smart_search-v2/deployment/
  pip install -r requirements.txt
  ```
  <img width="622" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/fe30b41d-4397-4164-ab78-ae6e3911981e">
+ export related enviormens variable
  ```javascript
  export AWS_ACCOUNT_ID={your account}
  export AWS_REGION={your region}
  ```
  Accound id:
  
  <img width="341" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/28032479-912e-4ef1-84df-f801e6d5d5ba">

  Region:
  
  <img width="319" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/336be76b-da28-4a15-b393-c8c2837a84e6">

  <img width="660" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/07a1f8a9-f319-415a-aca1-01668771dfe1">

+ deploy resource by cdk (total process will take around 30 mins)
    
   ```javascript
  cdk bootstrap
  cdk deploy --all --require-approval never
  ```
  <img width="1008" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/2802e7da-c643-47ad-99bf-e80182e27038">

  <img width="944" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/6d218036-bb4b-474a-a01c-a32380eb5e1a">

Step 4. Import Data to kendra from AWS S3
+ download related white paper
```javascript
  cd ~
  wget https://jameschiang1001.s3.amazonaws.com/AWS_Whitepapers.zip
  unzip AWS_Whitepapers.zip
  ```
+ check kendra s3 data source, go to s3 service and check bacuket name which initial from smart-search-kendraxxxx
  <img width="1341" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/44fc8f5b-b117-4ced-ac9f-a6ed4c871b73">

+ back to cloud9 console, use following command to upload white paper to s3
  ```javascript
  aws s3 sync  AWS_Whitepapers s3://smart-search-kendra-s3-source-bucket-444225271674-us-east-2/
  ```
  <img width="856" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/9c5239a5-4890-467f-bdec-ad8a53aec437">

+ back to kendra and click index
  <img width="1028" alt="image" src="https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/c4dc8b1f-f384-4766-9f2b-134e2ebeaf0c">

+ find the data source and click sync now
  ![image](https://github.com/JamesChiang1014/LLM-Workshop/assets/29404157/678d203d-28b6-4adf-8c76-027f45cf63a8)

+ 

  




