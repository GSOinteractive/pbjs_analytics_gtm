# Prebid.js analytics adapter  
  
pbjs_analytics_gtm is a Predid.js analytics adapter for Google Analytics integrated with Google Tag Manager.   
  
  
**Table of Content**  
- [GTM Setup](#GTM Setup)
- [Adapter Setup](#Adapter Setup)  
  
## GTM Setup
First you need to prepare your Google Tag Manager to collect events and send them to Google Analytics.  
You'll need 6 variables, 1 tag and 1 trigger.  
  
### GTM Variables  
- Create a "Google Analytics settings" variable with your Google Analytics Tracking ID. For the documentation we will name it 'GA Setup'  
- Create 5 Data Layer Variables with theses settings :
  - **Name** : Event Action, **Data Layer Variable Name** : eventAction, **Data Layer Version** : Version 2
  - **Name** : Event Category, **Data Layer Variable Name** : eventCategory, **Data Layer Version** : Version 2
  - **Name** : Event Label, **Data Layer Variable Name** : eventLabel, **Data Layer Version** : Version 2
  - **Name** : Event Value, **Data Layer Variable Name** : eventValue, **Data Layer Version** : Version 2
  - **Name** : Event Non Interaction, **Data Layer Variable Name** : eventNonInteraction, **Data Layer Version** : Version 1
  
![Variable configuration](https://user-images.githubusercontent.com/1268331/43193055-4d5aa0c0-8fff-11e8-918c-292f71e40f76.png)

### GTM Trigger  
- Create a Trigger with theses settings :
  - **Name** : event GAEvent
  - **Triger Type** :  Custom Event
  - **Event name** :  GAEvent
   
![Trigger configuration](https://user-images.githubusercontent.com/1268331/43193071-59bc4d14-8fff-11e8-9040-1f4149c7b3a8.png)

### GTM Tag
- Create a Tag with theses settings :
  - **Tag Type** : Google Analytics - Universal Analytics
  - **Track Type** :  Event
  - **Category** :  {{ Event Category }}
  - **Action** :  {{ Event Action }}
  - **Label** :  {{ Event Label }}
  - **Value** :  {{ Event Value }}
  - **Non-Interaction Hit** :  {{ Event Non Interaction }}
  - **Google Analytics settings** :  {{ GA Setup }}
    
![Tag configuration](https://user-images.githubusercontent.com/1268331/43193062-539e26aa-8fff-11e8-9af0-977d49aaefd5.png)  