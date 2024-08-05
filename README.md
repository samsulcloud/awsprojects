# awsprojects

**This lab walks you through how to create vpc endpoint for accessing s3 bucket from private ec2 instance using vpc endpoint (aws private link).**

Step 1: Create a VPC , you can refer to the screenshot and fill the boxes as per your convenience

<img width="598" alt="image" src="https://github.com/user-attachments/assets/9587e449-3fd1-4854-aac2-8120aaf688ad">

Step 2: Attache an IGW

<img width="504" alt="image" src="https://github.com/user-attachments/assets/0608aeae-00cb-4136-8064-0a5bcd2f2030">

<img width="856" alt="image" src="https://github.com/user-attachments/assets/6a255262-d9a1-460c-9107-b5ee86141cab">

<img width="856" alt="image" src="https://github.com/user-attachments/assets/0102369a-dcbd-477e-98d1-ae4f50ea5a06">

<img width="495" alt="image" src="https://github.com/user-attachments/assets/290a79a5-0e5e-424f-8398-514b9c764a4b">

<img width="854" alt="image" src="https://github.com/user-attachments/assets/b4bf4b37-a216-4eda-afb8-4ddf763edd03">

Step 3: 

Create a Public and Private Subnet

To create a subnet click on Subnets which is present in the VPC dashboard section on the side pan.
Click on the Create Subnet button.

<img width="952" alt="image" src="https://github.com/user-attachments/assets/efcbfec8-2e5a-4742-92c8-836698985f66">

<img width="527" alt="image" src="https://github.com/user-attachments/assets/91f8648d-2628-446d-9c3a-c8e6b93e13c6">

<img width="599" alt="image" src="https://github.com/user-attachments/assets/7d3a6fa2-a582-422a-8559-1efec1865638">

<img width="586" alt="image" src="https://github.com/user-attachments/assets/dca661fc-287c-4b1d-a1f7-0150de4abb52">

<img width="795" alt="image" src="https://github.com/user-attachments/assets/bfc6c4cd-5f41-4554-93cb-483920cbc733">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/d0db2ce5-c44b-4606-b162-db09da12c8b0">

Step 4: Configure the Public subnet to enable auto-assign public IPv4 address

Go to VPC, do the following steps

Select the Public subnet

<img width="805" alt="image" src="https://github.com/user-attachments/assets/d09d1a7f-5884-4c84-84d1-13cb87fc8269">

Click on the Actions button

Choose Edit subnet settings from the options.

<img width="588" alt="image" src="https://github.com/user-attachments/assets/045f24cf-9ae6-4e0a-9c95-71ca42dc4134">

Step 6: Create a Route Table for the Public subnet

<img width="959" alt="image" src="https://github.com/user-attachments/assets/18d2916a-b41a-4de3-913a-82441e12556d">

<img width="575" alt="image" src="https://github.com/user-attachments/assets/63c3b331-8925-4a77-80c5-7bce60fb16cd">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/c8b57d84-e035-40d1-a666-a5a2590e8c2e">

Create one more route table for private routing

<img width="748" alt="image" src="https://github.com/user-attachments/assets/d49f8985-2100-4f92-864c-eecedfaf70dd">

Now we can associate the subnets to the route tables.

<img width="954" alt="image" src="https://github.com/user-attachments/assets/5dbb8bd1-6cce-4146-af9e-26fec9293b0e">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/e5fce9be-fddc-4ae1-aa2e-843c245ea780">

<img width="955" alt="image" src="https://github.com/user-attachments/assets/4e41024d-4638-4f3c-bd04-8c32ba167fb2">

<img width="950" alt="image" src="https://github.com/user-attachments/assets/ac4b94d7-398c-4f84-bf91-342b49e3bbc8">

In the sampubrt, Add a route to allow Internet traffic to the VPC.

<img width="955" alt="image" src="https://github.com/user-attachments/assets/d40a0189-9733-4293-a083-876fdd38b2bf">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/c1d85a9e-f895-42b4-a7e2-c1daebcd1bef">

Step 7:

Create Security groups

we need to create 2 security group one for bastion/jump server and another for allowing private instances to access vpc endpoint
navigate to ec2/vpc dashboard and create security groups

<img width="959" alt="image" src="https://github.com/user-attachments/assets/85253aed-d7fe-44de-b40d-8b4ba0f597a1">

We allow 80,443(http(s)), 22(ssh)

<img width="959" alt="image" src="https://github.com/user-attachments/assets/6ae5cdec-c98e-4347-800b-14590b5526cc">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/e7ed0641-35cb-4f88-a2cb-b88616936a7b">

<img width="958" alt="image" src="https://github.com/user-attachments/assets/54803b81-ddfa-4a2c-8f2b-cd78404c6cd8">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/d4ffc6ad-d6f4-41ce-99d3-3681aaca9086">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/227ed303-61e3-481d-946e-9e7647dc14ca">

Step 8:

Create a Jump host that should be publicly accessible 

<img width="526" alt="image" src="https://github.com/user-attachments/assets/e1aff4aa-1f7d-45ad-aa5c-2be116bc0272">

<img width="527" alt="image" src="https://github.com/user-attachments/assets/70bc3ceb-4610-4502-8c28-7c679fdcf402">

<img width="887" alt="image" src="https://github.com/user-attachments/assets/ef933af4-7633-4d21-91ab-fd4aaf9822cb">

<img width="527" alt="image" src="https://github.com/user-attachments/assets/be857c86-4c4d-418f-bcc8-b195cb7fc880">

<img width="953" alt="image" src="https://github.com/user-attachments/assets/693bad07-fdd1-4fd8-a41d-c1db3c5988e3">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/cd1a00ab-fbe8-4431-af84-d35344f3c7de">

Create a private ec2 instance for accessing s3 using vpc endpoint

<img width="950" alt="image" src="https://github.com/user-attachments/assets/37d60f05-0aad-4e92-975f-9b97f27f73d9">

<img width="526" alt="image" src="https://github.com/user-attachments/assets/1713b2c9-f5f1-44cf-93ee-3514ccba8664">

<img width="524" alt="image" src="https://github.com/user-attachments/assets/e46d14bd-ec78-4394-8d0f-6cb0ee6f181e">

<img width="526" alt="image" src="https://github.com/user-attachments/assets/518a4c96-f8fa-4f57-82bd-8b2839e426b9">

<img width="527" alt="image" src="https://github.com/user-attachments/assets/ea3bb586-bdcf-498c-95b6-f81a098503b4">

<img width="761" alt="image" src="https://github.com/user-attachments/assets/a8a6f789-e15b-4d43-bdbd-437a1636f5a7">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/cd082b08-d266-4077-bbb9-f6038c978d9d">

Step 9: Access the private ec2 via jumpserver

<img width="757" alt="image" src="https://github.com/user-attachments/assets/1ef397e1-7d70-440b-8f86-754931602bce">

<img width="823" alt="image" src="https://github.com/user-attachments/assets/4b6eacfc-5543-4e8c-992f-5b8bc48bd9ad">

<img width="883" alt="image" src="https://github.com/user-attachments/assets/3034436e-8a9b-40c7-8567-68fcf1baed99">

<img width="725" alt="image" src="https://github.com/user-attachments/assets/e185c9f2-5c4f-4b29-abf3-5f9b809c79e2">

<img width="784" alt="image" src="https://github.com/user-attachments/assets/705ca903-c10c-4acd-af6a-ab0ec6314a84">

<img width="728" alt="image" src="https://github.com/user-attachments/assets/09ec45d2-d05b-4007-bb99-01dcecf58545">

<img width="790" alt="image" src="https://github.com/user-attachments/assets/403a941f-a73e-4c78-8e4b-9be602fc2e47">

Here comes the last step

Step 10: Create a VPC Gateway Endpoint for S3, it adds automatically to private route table

<img width="959" alt="image" src="https://github.com/user-attachments/assets/f8f483fd-f0b9-4121-a54b-f86638d4b00d">

<img width="956" alt="image" src="https://github.com/user-attachments/assets/4153f064-76d9-48f7-8f04-e030d920c7ac">

<img width="957" alt="image" src="https://github.com/user-attachments/assets/2dfc225b-c346-46cf-a4fb-81d5e394fc10">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/748ff216-89ae-4053-9952-e877225a5629">

<img width="958" alt="image" src="https://github.com/user-attachments/assets/65c85f6e-4188-4483-9a20-2ea1f2652a2a">

<img width="491" alt="image" src="https://github.com/user-attachments/assets/432d11a4-000f-4604-8f67-93b13dfe5ff1">

<img width="902" alt="image" src="https://github.com/user-attachments/assets/6d31ba03-fc85-4c78-b514-da9e72a35c4b">































































