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


- **Step: 1**

Once you have successfully downloaded the Azure Auth Bot sample, now go to your azure portal and hit the `Create a  Resource` Icon then search for `Azure Bot` you should get the below screen.

<img src="https://i.stack.imgur.com/T1FXR.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  


- **Step: 2**

Once you got the `Azure Bot` option successfully now configure your bot as per your `Subscription` and `Resource Group` as below.


<img src="https://i.stack.imgur.com/ksgzX.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  

**Note:** Make sure you have selected `Multi-Tenant` as `type of App`. Otherwise, you might encounter `401` while requesting the token from `Azure Bot` to `Azure Active Directory. Because the entire token has been issued from `Azure Active Directory Service`. Here you should additionally know, that `Azure Bot` is a different service. 

- **Step: 3**

Now go to your `bot channel resource` and click on `Add OAuth Connection Settings` you should get the below screen. 

<img src="https://i.stack.imgur.com/M7oC8.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  

**Note:** To get `app Id` , `app secret` and `tenant id` click on `Microsoft App ID` on `step 3`. Here is the screenshot for your reference.

- **app Id-Client Id / Tenanat Id**

<img src="https://i.stack.imgur.com/QeZQS.png" alt="user avatar" width="950" height="550" class="bar-sm bar-md d-block">  

- **App Secret**

<img src="https://i.stack.imgur.com/wO3gW.png" alt="user avatar" width="950" height="550" class="bar-sm bar-md d-block"> 

**Be informed that `Token Exchange URL` will be empty and `Scopes` should be `openid profile`. Just copy and paste from here 😁.** 


## Configure Bot App Permission On Azure Active Directory Graph API
- **Step: 1: Set Redirect URL**

<img src="https://i.stack.imgur.com/B9xfJ.png" alt="user avatar" width="950" height="550" class="bar-sm bar-md d-block"> 

**Note:** Your can copy the redirect URL from here: Remember that you have to add both the `URL`
```
          https://token.botframework.com/.auth/web/redirect
          https://token.botframework.com
```

- **Step: 2: Set Microsoft Graph Permission**

Now you should set the correct `Delegated permissions` on `Microsoft graph API` under `Azure Active Directory` as per the below screenshot.

<img src="https://i.stack.imgur.com/YrpVP.png" alt="user avatar" width="950" height="550" class="bar-sm bar-md d-block"> 
<img src="https://i.stack.imgur.com/I2kRb.png" alt="user avatar" width="950" height="450" class="bar-sm bar-md d-block"> 
<img src="https://i.stack.imgur.com/UcO4w.png" alt="user avatar" width="950" height="450" class="bar-sm bar-md d-block"> 
<img src="https://i.stack.imgur.com/J6x6e.png" alt="user avatar" width="950" height="350" class="bar-sm bar-md d-block"> 

## Check and Test the Bot Permission

If you have followed the above steps correctly, you can now test your permission if that is working accordingly as below:

<img src="https://i.stack.imgur.com/sXbZr.gif" alt="user avatar" width="850" height="650" class="bar-sm bar-md d-block">  

## Configure Your Bot Project On Visual Studio

Now go to `appsettings.json` file on your visual studio bot project and configure the below 3 properties as per your Azure Bot Information. 

```
{
  "MicrosoftAppId": "",
  "MicrosoftAppPassword": "",
  "ConnectionName": "AuthBot"
}
```
You can get above information here:
- **MicrosoftAppId**

<img src="https://i.stack.imgur.com/QeZQS.png" alt="user avatar" width="950" height="550" class="bar-sm bar-md d-block">  

- **MicrosoftAppPassword**

<img src="https://i.stack.imgur.com/wO3gW.png" alt="user avatar" width="950" height="550" class="bar-sm bar-md d-block"> 

- **ConnectionName**
Go to your `bot channel resource`then `Configuration` and click on `OAuth Connection Name` you should get the below screen. 

<img src="https://i.stack.imgur.com/M7oC8.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  

## Publish Bot Project From Visual Studio

Here select your `app service` or you can `create new app service` for your bot. You can see the below screen shot. 

## Copy App Service URL 

Your service `URL` should be like this `https://YourBotAppService.azurewebsites.net`

<img src="https://i.stack.imgur.com/JjL05.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  

## Configure Bot Messaging endpoint 

Now Copy your `Bot service URL` and go to your `BOT` then click on `Configuration` and paste the `URL` at `Messaging endpoint` with `suffix` value `api/messages` altogether your `Messaging endpoint URL` would be `https://YourBotAppService.azurewebsites.net/api/messages`. Just like below:

<img src="https://i.stack.imgur.com/IzTXH.png" alt="user avatar" width="950" height="750" class="bar-sm bar-md d-block">  

You have successfully configured the azure authentication bot sample. If you still encounter any problems you could post your issue on [stackoverflow.com](https://stackoverflow.com/users/9663070/md-farid-uddin-kiron) . I will help you there if you need it. 
