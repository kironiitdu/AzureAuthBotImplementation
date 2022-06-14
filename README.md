# Azure Auth Bot Implementation
You might want to implement Azure Authentication Bot into your Bot Application which has been explained [here in Microsoft Official Document](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-authentication?view=azure-bot-service-4.0&tabs=userassigned%2Caadv2%2Ccsharp)   but you are still struggling. This example will provide you with details guidelines to practically implement the Authentication Bot example as below


## Output

<img src="https://i.stack.imgur.com/uZMqt.gif" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  


## What Do you need/ Prerequisite 
 - [Azure Auth Bot Sample](https://github.com/microsoft/BotBuilder-Samples/tree/main/samples/csharp_dotnetcore/18.bot-authentication)  
 - [Azure Bot Resource](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-authentication?view=azure-bot-service-4.0&tabs=userassigned%2Caadv2%2Ccsharp#create-the-resource)   
- [Visual Studio 2019 or Latest Version]( https://visualstudio.microsoft.com/)  

## Download The Azure Auth Bot Sample From GitHub Repository 
[Down Load Azure Auth Bot Sample From Microsoft Official Github](https://github.com/microsoft/BotBuilder-Samples/tree/main/samples/csharp_dotnetcore/18.bot-authentication)  

## Create Azure Bot 


- **Step: 1: **

Once you have successfully downloaded the Azure Auth Bot sample, now go to your azure portal and hit the `Create a  Resource` Icon then search for `Azure Bot` you should get the below screen.

<img src="https://i.stack.imgur.com/T1FXR.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  


- **Step: 2**

Once you got the `Azure Bot` option successfully now configure your bot as per your `Subscription` and `Resource Group` as below.


<img src="https://i.stack.imgur.com/ksgzX.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  

**Note:** Make sure you have selected `Multi-Tenant` as `type of App`. Otherwise, you might encounter `401` while requesting the token from `Azure Bot` to `Azure Active Directory. Because the entire token has been issued from `Azure Active Directory Service`. Here you should additionally know, that `Azure Bot` is a different service. 

## Configure Bot App On Azure Active Directory 


