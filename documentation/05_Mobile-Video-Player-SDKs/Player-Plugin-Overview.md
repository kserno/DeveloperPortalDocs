---
layout: page
title: Player Plugin Overview
---

[![iOS](https://img.shields.io/badge/iOS-Supported-green.svg)](https://github.com/kaltura/player-sdk-native-ios)
[![Android](https://img.shields.io/badge/Android-Supported-green.svg)](https://github.com/kaltura/player-sdk-native-ios)

This article provides an overview of the plugins for the Kaltura Player. 

## Introduction
A plugin for the Kaltura Player uses a combination of HTML, JavaScript and/or CSS to customize the Player, enabling you to apply any feature that can be added to a web page to be be added using a plugin.

At a high level, a plugin integrates with the Player by listening to and emitting events.

The plugins can be developed to:

* Modify default behavior
* Add functionality
* Customize appearance

## Kaltura Plugins
The following are the Kaltura-provided plugins that you can implement in your system:
{% extlink Kaltura Player Plugins https://vpaas.kaltura.com/documentation/player-sdk/Player-Plugins-in-the-SDK-Supported-plugins#sthash.3a8Dft10.dpbs %}.

## How to Enable/Create a Plugin

#### Using an Existing Plugin

1. If you want to change/add a plugin, the key should begin with the plugin name, dot and the plugin attribute. Every plugin includes the plugin attributes required for enabling or disabling the plugin.
2. In order to add plugin, use the addConfigKey ({% extlink iOS https://github.com/kaltura/player-sdk-native-ios/blob/master/KALTURAPlayerSDK/KPPlayerConfig.h#L57 %}, {% extlink Android https://github.com/kaltura/player-sdk-native-android/blob/master/playerSDK/src/main/java/com/kaltura/playersdk/KPPlayerConfig.java#L86%}) function. Note that the first parameter takes the key name and the second takes the value.

In this example, the loadingSpinner plugin has been disabled:

```
// objective_c
[config addConfigKey:@"loadingSpinner.plugin" withValue:@"false"];
```
```
// Java
config.addConfig("loadingSpinner.plugin", "false");
```

#### Creating Custom Plugins

To create custome plugins, follow the steps in the article {% extlink Extending the Player with Plugins https://vpaas.kaltura.com/documentation/media-player/Player-Plugins#sthash.gtmiiI7F.dpbs %}.

### How to Detect if Configured Plugins are Loaded
1. Open the iOS Player API base by following the steps in the article {% extlink Accessing the iOS player API Base Methods https://vpaas.kaltura.com/documentation/player-sdk/Kaltura-iOS-player-API-Base-Methods#sthash.ObDzzCgb.spB9h8rA.dpbs %}.
2. Follow the instructions in * "Receiving  Notification when the Player API Is Ready" to detect if configured plugins are loaded.

### How to Get Notified about Player Plugin-Related Callbacks
1. Open the iOS Player API base by following the steps in the article {% extlink Accessing the iOS player API Base Methods https://vpaas.kaltura.com/documentation/player-sdk/Kaltura-iOS-player-API-Base-Methods#sthash.ObDzzCgb.spB9h8rA.dpbs %}.
2. Follow the instructions in * addKPlayerEventListener * to receive notifications about Player plugin-related callbacks.