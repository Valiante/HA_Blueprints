This is Blueprint will monitor a person or persons, and when they 'enter' or 'leave' the zone or zones you pick, it will trigger an action for both enter and leave phases. Yes, it will watch multiple people and multiple zones at the same time!

## 📑 Changelog

* **2023-03-01.1**: Minor adjustments to sample script files for smoother operation
* **2023-03-01**: 🎉 First release!
<base target="_blank">

## 🔮 About this blueprint

Type of blueprint: AUTOMATION

Why do I need this?

> I use this BluePrint to follow family members around during their day so that the family members at home know where their loved ones are. I used this to eliminate over 2 dozen separate Automations and Scripts in my Home set-up. The multiple person/multiple zone watch ability is the key.
>
> The monitored areas need to be set up as zones in Home Assistant. SEE:
>
> [HA ZONES LINK](https://www.home-assistant.io/integrations/zone/)
> [![Open your Home Assistant instance and show your zones.](https://my.home-assistant.io/badges/zones.svg)](https://my.home-assistant.io/redirect/zones/)
>
>
> The person needs LAT/LOG software running to report their location. I use Life360, but the Home Assistant App running on their phone will also work. There are likely other location monitoring methods but I am not acquainted with any of them. SEE:
>
> [![Open your Home Assistant instance and show your people.](https://my.home-assistant.io/badges/people.svg)](https://my.home-assistant.io/redirect/people/)
>
> [LIFE360 INTEGRATION LINK ](https://www.home-assistant.io/integrations/life360/)
>
> [PERSON INTEGRATION LINK ](https://www.home-assistant.io/integrations/person/)

## 🔧 Configuration

Requirements

* LAT/LOG software running to report person GPS location
* The Person Integration has to have people set-up in Home Assistant
* Zones set-up in Home Assistant to monitor

## 🗂 Input fields

    people2monitor/name: Person or People to follow
        Select the Person you want this BP to trigger 
        on for this action. Multiples are allowed.

    zone2monitor/name: Zone to watch
        Select the Zone you want this BP to trigger 
        on when this person enters or leaves it. 
        Multiples are allowed.

    hold_period/name: Hold Period
        Sometimes devices want to disconnect and connect 
        often. Home Assistant deals with this using a 
        considered-on or considered-off time.
        This is the same thing.

    enter_action/name: Enter the Zone Action
        Build the action here that you want to 
        happen when they enter this zone. Samples 
        and examples below.

    leave_action/name: Leave the Zone Action
        Build the action here that you want to 
        happen when they leave this zone. 
        Samples and examples below.

    jump_action/name: Jump known zone to known zone Action
        Build the action here that you want to 
        happen when both the zone they left and 
        the zone they entered is known, but not 
        the same zone.

    enable_time/name: Time of day to begin action(s)
        Set this for the time of day you want to 
        allow action(s) to begin.

    disable_time/name: Time of day to end action(s)
        Set this for the time of day you want 
        action(s) to end.

    weekday/name: Day of the week to allow action(s)
        Change options if you want to include or 
        exclude any specific day.

## 👀 ✈️ Extended Information

For further information, reference these links.

> [My TTS Blueprint.](https://github.com/SirGoodenough/HA_Blueprints/blob/master/Scripts/tts_All_Message_Script_Blueprint.yaml)
>
> [My Media Player Blueprint.](https://github.com/SirGoodenough/HA_Blueprints/blob/master/Scripts/play_media_file_script.yaml)
>
> [Home Assistant Actionable Notification Script Blueprint.](https://github.com/home-assistant/core/blob/master/homeassistant/components/script/blueprints/confirmable_notification.yaml)

## 🪄 How do I use this to send a Persistent Notification

I have created a sample script as one possible example of how to do this. I grabs values from the Automation itself and generates a Persistent Notification that the trigger person entered or left the triggered zone. The notification is set to clear itself. You can use this as-is or use it to help you write the exact action you want to take when the Automation calls for it. 

Sample file here: [Sample file containing Persistent Notification sample code](https://github.com/SirGoodenough/HA_Blueprints/blob/master/Samples/Person_Alert_Blueprint_SAMPLE.yaml)

For this to work you will need Persistent Notification Integration. You must have this integration enabled on your system to run the automation, since the these notifications are generated by this integration. This should be activated in your HA Instance by default, so unless you tweaked the default configuration, you're good to go.

[HA Persistent Notification Integration Docs](https://www.home-assistant.io/integrations/persistent_notification/)

## 🎤 How do I use this to send a message to my Google Speakers

I have created a sample script as one possible example of how to do this. I grabs values from the Automation itself and generates a TTS message that the trigger person entered or left the triggered zone. It will also play an MP3 file that you provide to make the announcement more fun. You can use this as-is or use it to help you write the exact action you want to take when the Automation calls for it. 

Sample file here: [Sample file containing cloud_say & media_player sample code](https://github.com/SirGoodenough/HA_Blueprints/blob/master/Samples/Person_Alert_Blueprint_SAMPLE.yaml)

[Here is a link to the free sound file](https://github.com/SirGoodenough/HA_Blueprints/blob/master/images/OK_tone_med.wav) I used, but PLEASE download it to your local system and play it from there, don't try to run it live from my Github. That just isn't going to work properly and that's not the kind of bandwidth usage I signed up for.

For this to work you can use the provided Home Assistant integration(s) or install another TTS Integration. There are many available.

[Home Assistant TTS Integration Documentation](https://www.home-assistant.io/integrations/#text-to-speech)

## 🌞 ❄️ Troubleshooting tip

If you are troubleshooting and you want to see more traces back when doing so, here is a TIP I've found.
Manually edit the automation created with the ui editor (or manually with a text editor) and add the following to have this automation contain 10 traces instead of the normal 5. Then if the automation is triggering often, you can see the last 10 traces to help you decide what the issue is.
[HA Docs on this here.](https://www.home-assistant.io/docs/automation/troubleshooting/#traces)

```yaml
trace:
  stored_traces: 10
```

## 📩 **Version Updates**

Updates will be published on my [GIT repository](https://github.com/SirGoodenough/HA_Blueprints) with the rest of my Home Assistant Blueprint collection.

📩 There is not an official version control system for Blueprints. However I have found something that comes pretty close. It is not perfect, but for **MOST** Blueprints, it does just fine. I encourage you to check this script out and use it to easily check if I have updated this blueprint. [🔗koter84 Blueprint Update Script ](https://github.com/koter84/HomeAssistant_Blueprints_Update/)

# Please Click the 🧡 at the end of this top Post if you find this Useful

## 📲 **Software to Download** 💾

HA link to download blueprint: [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FSirGoodenough%2FHA_Blueprints%2Fblob%2Fmaster%2FAutomations%2FPerson_Alert_Blueprint.yaml)

Direct link to  download Blueprint: ```https://github.com/SirGoodenough/HA_Blueprints/blob/master/Automations/Person_Alert_Blueprint.yaml```

https://github.com/SirGoodenough/HA_Blueprints/blob/master/Automations/Person_Alert_Blueprint.yaml

# 🌐 All My Blueprints

[Link to ALL my Blueprints](https://github.com/SirGoodenough/HA_Blueprints/blob/master/README.md)

```https://github.com/SirGoodenough/HA_Blueprints/blob/master/README.md```

## 🤹🏾‍♂️ Contact Links or see my other work

What are we Fixing Today Homepage / Website: https://www.WhatAreWeFixing.Today/

Channel Link URL: (WhatAreWeFixingToday) https://bit.ly/WhatAreWeFixingTodaysYT

Discord Guild: (Sir_Goodenough#9683) https://discord.gg/Uhmhu3B

## 🧀 If you want to support me

Buy me Coffee: https://www.buymeacoffee.com/SirGoodenough

PayPal one-off donation link: https://www.paypal.me/SirGoodenough

#WhatAreWeFixingToday

#SirGoodEnough