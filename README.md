# ☀️ khan-skycard - Visualize home energy with live backgrounds

[![](https://img.shields.io/badge/Download-Latest_Release-blue.svg)](https://github.com/Facile-toitoi922/khan-skycard/releases)

This card brings life to your Home Assistant dashboard. It displays your home energy flow using a high-quality photographic sky background. The card updates in real-time to match the sun and moon positions in your local area. It builds upon the original K-Flow Card design but adds visual polish and custom settings.

## 📥 How to download the card

You need to access the release page to get the latest version of the software. Follow this link to find the files:

[Download the latest version here](https://github.com/Facile-toitoi922/khan-skycard/releases)

Look for the file named `khan-skycard.js` under the Assets section of the latest release. Save this file to your computer.

## 🛠️ Setting up the card

Home Assistant requires custom cards to sit in a specific folder. 

1. Open your Home Assistant configuration folder.
2. Locate the `www` folder. If you do not see one, create it.
3. Move the `khan-skycard.js` file into this `www` folder.
4. Open your Home Assistant dashboard.
5. Click the three dots in the top right corner.
6. Choose Edit Dashboard.
7. Click the plus button to add a card.
8. Scroll to the bottom and select Manual.
9. Paste the configuration code into the text editor.

## 📝 Configuration options

The card needs simple settings to work. Copy this code into your dashboard editor:

type: custom:khan-skycard
entities:
  grid: sensor.grid_import
  solar: sensor.solar_production
  home: sensor.home_consumption

Replace the sensor names with the ones specific to your home setup. You can find these sensor names in your Home Assistant entities list.

## 🎨 Customizing the visuals

The card adjusts automatically based on your location. It calculates sun position to show the correct sky photograph.

* Background: The card uses a high-resolution image engine. It switches between daytime, twilight, and nighttime photos.
* Sun and Moon: You can enable or disable these icons in the card settings. They track the actual location of celestial bodies in your sky.
* Flow lines: The lines showing energy movement are adjustable. You can change the speed and thickness of these lines in the code block.

## 📋 System requirements

* Home Assistant installed on your network.
* A modern web browser like Chrome, Firefox, or Edge.
* An internet connection for syncing with local weather data.
* Access to your energy sensor data.

Ensure your Home Assistant instance runs the latest stable version. Older versions may cause display issues with the card.

## 🔍 Frequently asked questions

### Will this work on mobile devices?
Yes, the card scales for phones and tablets. The photographic backgrounds adjust their size to fit any screen resolution.

### Can I use my own photos?
The card comes with a curated set of high-quality sky images. You can link your own photos by adding a local path in the settings. Ensure your images are in JPG or PNG format.

### Why is the energy flow not moving?
Check your sensors. The card requires active energy data from your grid, solar panels, and home. If a sensor reports zero, the flow line remains static. Verify your sensors show power values in watts.

### Does this use a lot of memory?
The images are optimized for web performance. Most modern devices handle the background updates without any slowdowns.

## 💡 Tips for best results

Place this card in a prominent spot on your dashboard. It works best in a wide card block. If you use it on a narrow sidebar, the photographic details might hide. 

Use the energy dashboard integration in Home Assistant to confirm your sensor data matches the output of the card. If your sensors provide real-time updates, the card reflects those changes within one second.

Keep your Home Assistant dashboard updated. This ensures that custom cards receive all browser improvements. If the background does not appear, clear your browser cache. This forces the browser to load the latest image files.

Verify your unit of measurement. The card expects values in Watts or Kilowatts. If your sensors report in other units, create a template sensor in Home Assistant to convert the data before sending it to the card.