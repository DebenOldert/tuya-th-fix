# UPDATE 20250214:
Scratch the update below. This component now also fixes #136472 by adding support for some Temperature and 
Humidity Sensors (with External Probe).   
Thus, as Tuya keeps messing around (to be nice), this component will likely serve a while longer as testing platform 
and /or temporary replacement.      
Can't be bothered to update the README right now ;)

# UPDATE 20250213:
PR #136960 has been merged into /home-assistant/core/tree/dev, closing issue #132844. 
This means the official Tuya Integration will have this fix incorporated in a future Home Assistant release,
rendering this custom integration obsolete. 

I will not archive this repo at least until then, and probably a bit longer for those not so fast with upgrading. 

# Tuya - LSC Camera Fix (tuya-lsc_camera_fix)
Custom Tuya component for Home Assistant which fixes support for some LSC Connect cameras.
Can be used as replacement or alongside the build-in Tuya integration.

All credits go to @Neirop for his research on the solution. 
Also see https://github.com/home-assistant/core/issues/132844

## The fix
Most Tuya cameras are in the category "sp". About two months ago Tuya suddenly changed the category on some camera's,
mostly of the LSC Smart Connect brand sold by Action stores in Europe, to "dghsxj".
Thanks to @MPParsley contact with customer support we now know "dghsxj" is a new (but undocumented) category for _Low power consumption cameras_.

This custom component simply adds that category to CAMERAS and creates all the same device properties as in the "sp"
category.

## Installation
### Manual installation
Upload the _tuya-lsc_camera_fix_ directory to your _~/homeassistant/custom_components/_ directory.

### HACS
Make sure you have HACS installed.

* Navigate to HACS
* Click the 3-dot menu in the top-right corner, choose **Custom Repositories**. In the form fill out the following:
  * **Repository:** this repo; _maghiel/tuya-lsc_camera_fix/_
  * **Type:** _Integration
  * Click **Add**

The repo will now be downloaded. Restart Home Assistant after a successful download. 

* Navigate to _Settings > Devices & Services_
* Click _Add Integration_
* Search for _Tuya LSC Camera Fix_ and install the integration. 
