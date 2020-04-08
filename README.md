# HomeAssistant app for Splunk
This is a Splunk app designed to be used with the [HomeAssistant](https://home-assistant.io) home automation platform, to give you more insight into your system.

## Requirements
* You need to have at least Splunk 6.3 installed, since this uses the HTTP Event Collector introduced in that version.
* HomeAssistant installed on a machine that can connect to the one running Splunk.

## Installation
* Install the app by copying the `homeassistant` directory to `$SPLUNK_HOME/etc/apps/homeassistant` and restarting Splunk so that the app is recognized.
* At this moment, you must manually enable the HTTP Event Collector and add a token for HomeAssistant:
* To Enable the HEC
  - Go Settings > Data Inputs and choose HTTP Event Collector
  - For "All Tokens", select "Enabled", and click "Save"
* To Create a New Token
  - Choose "New Token"
  - Give your token a name and click "Next"
  - Under "Source type", choose "Select", and then "Structured > _json"
  - Under Index, select your desired index. I recommend using index=hass or index=homeassistant
 - When you're done, you'll be given the "Token Value".  Place this in your HomeAssistant configuration as per the Splunk component's documentation.
* If you are not using index=hass or index=homeassistant
  - Go to Settings > Advanced search > Search macros 
  - Edit 'homeassistant_index' and update the search to point to your desired index.
* Finally, you need to complete the configuration from within home assistant.
  - Follow the documentation here: https://www.home-assistant.io/integrations/splunk/

## Features
* Provides analogues to HomeAssistant's native reporting, including a range-configurable History view and a filterable logbook.
* Provides a Device Tracker view that shows time spent per location/device
* Provides an Energy Usage dashboard (although this may need to be customized to your HomeAssistant configuration)
