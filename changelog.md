# Changelog

## 4/7/2020
- Added macro to allow index to be specified globally, instead of forcing user to update all dashboards if they are not using index=homeassistant.
  * The macro will default to look for index=hass OR index=homeassistant
- Removed the horrible props.conf. Updated Readme to specify to use sourcetype=_json instead.
- Updated dashboard panels, to work with above marcos, and to allow better UI/choice design options.
- Started working on a current status dashboard.
- The logbook dashboard is more presentable now.
