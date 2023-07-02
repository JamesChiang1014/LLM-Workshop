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





