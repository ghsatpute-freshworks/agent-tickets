# Freshdesk Agent's Saved Tickets App

## Description 
This app allows an agent to add tickets to current working list or the tickets he wants to visit later.

## App Demo 

![App Demo](demo.gif)

## Prerequisites:
* Make sure you have a trial Freshdesk account created
* Ensure that you have the FreshWorks Developer Kit (FDK) installed properly.

## How to run the app 
* Go to parent directory of this app 
* Run `fdk run` command 
* Go to http://localhost:10001/custom_configs 
* Give your FreshWorks domain prefix. 
  
  For example, if the complete URL is 
  https://abcd1234.freshdesk.com, then enter `abcd1234` in `Fresh Desk Domain Prefix` parameter
* Visit tickets page https://abcd1234.freshdesk.com/a/tickets/7?dev=true.
  
  Remember to replace your account number. 
* You'll see an app as shown in App Demo 

## Development Platform Features used in this app

| Feature | Purpose | 
| --- | --- | 
| App lifecycle methods | To load current agent tickets on the loading of app | 
| Serverless app | Data operations are performed on server side instead of client side for persistent store |
| Installation Parameters | We ask the user the FreshWorks domain prefix so that the ticket URL can be formed properly | 
| Data Storage & Storage API | To store/retrieve/delete the tickets of agent |
| Data Method | 1. To get current logged in user details <br/>2.  To get current domain <br/> 3. To get current ticket details | 
| Server Method Invocation | Calling server side to store/retrieve/delete data |
| Instance Method | To resize the app size |


### Few problems
* The ticket link could be opened in new window (to provide better UX), but it fails with below error
    ```
    Unsafe attempt to initiate navigation for frame with origin 'https://newaccount1619511084587.freshdesk.com' from frame with URL 'http://localhost:10001/iframe/index.html?appId=123456789'. The frame attempting navigation of the top-level window is sandboxed, but the flag of 'allow-top-navigation' or 'allow-top-navigation-by-user-activation' is not set.
    ```
  so for now, I'm opening tickets in a new tab.
* As of now, app widget cannot be resized. So the column "remove ticket" looks bit weird.  
