# Home Assistant app for Splunk
This is a Splunk app designed to be used with the [Home Assistant](https://home-assistant.io) home automation platform, to give you more insight into your system.

## Requirements
* You need to have at least Splunk 6.3 installed, since this uses the HTTP Event Collector introduced in that version.
* Home Assistant installed on a machine that can connect to the one running Splunk.

## Installation
1. Install the app by copying the `homeassistant` directory to `$SPLUNK_HOME/etc/apps/homeassistant` and restarting Splunk so that the app is recognized.
2. Create an index for home assistant (For basic configuration, you can skip this step.)
    - Goto Settings > Indexes, Click New Index
    - Pick an index name. I recommend "homeassistant" or "hass"
    - Leave the other options as default.
    - Click Save
3. Enable the Http Event Collector
    - To Enable the HEC
    - Go Settings > Data Inputs and choose HTTP Event Collector
    - For "All Tokens", select "Enabled", and click "Save"
4. Create a new HEC Token
    - Choose "New Token"
    - Give your token a name and click "Next"
    - Under "Source type", choose "Select", and then "Structured > _json"
    - Under Index, select your desired index. Select the index you created in the 2nd step.
    - When you're done, you'll be given the "Token Value".  Place this in your Home Assistant configuration as per the Splunk component's documentation.
5. If you are not using index=hass or index=homeassistant (For basic configuration, you can skip this step.)
    - Go to Settings > Advanced search > Search macros 
    - Edit 'homeassistant_index' and update the search to point to your desired index.
6. Finally, you need to complete the configuration from within home assistant.
    - Follow the documentation here: https://www.home-assistant.io/integrations/splunk/

## Features
* Provides analogues to Home Assistant's native reporting, including a range-configurable History view and a filterable logbook.
* Provides a Device Tracker view that shows time spent per location/device
* Provides an Energy Usage dashboard (although this may need to be customized to your Home Assistant configuration)
