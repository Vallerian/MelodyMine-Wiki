---
description: MelodyMine Key Features
---

# ✨ Features

## AdminMode

You can communicate with all players in the voice chat or listen to their voices using AdminMode capability, which can be toggled using the command `/melodymine adminmode`.

<div align="left" data-full-width="false">

<figure><img src="https://i.ibb.co/TYbYYPK/Screenshot-2023-10-04-113549.png" alt=""><figcaption></figcaption></figure>

</div>

***

## Server  Mute / Unmute

You can server mute players in the voice chat , preventing muted players from speaking and only allowing them to hear others' voices.&#x20;

{% hint style="info" %}
This capability is accessible through the command `/melodymine mute <player>` to mute a player and `/melodymine unmute <player>` to unmute them.
{% endhint %}

<div align="left">

<figure><img src="https://i.ibb.co/4dB3RTM/Screenshot-2023-10-04-114141.png" alt=""><figcaption></figcaption></figure>

</div>

***

## Proxy-Less

You can deploy the MelodyMine plugin across multiple servers and manage them all from one website without the need for proxies.&#x20;

After installing the MelodyMine website, you can add the MelodyMine plugin to as many Minecraft servers as desired.&#x20;

MelodyMine does not require installation on `Velocity` or `BungeeCord`, and it automatically transfers the voice of a player who switches servers. No action is required on the website.

{% hint style="warning" %}
Ensure that in the configuration files of each server, the server name config related to `server` is unique and not duplicated.
{% endhint %}

***

## AuthMe Support

The MelodyMine plugin supports the [AuthMe](https://www.spigotmc.org/resources/authmereloaded.6269/) plugin, allowing players to join the Minecraft server with their `AuthMe` username and password without needing to be online on the Minecraft server.

{% hint style="warning" %}
To enable this capability, both the MelodyMine and the `Authme` table must be present in a same database.
{% endhint %}

<div align="left">

<figure><img src="https://i.ibb.co/tLB1vyg/image.png" alt=""><figcaption></figcaption></figure>

</div>

***

## Automatic Login

You can automatically log in to the website by using the command `/melodymine start link`, which provides you with a link. \
\
Clicking on this link automatically log n you into the website, allowing you to use the voice chat without needing to log in separately.

<div align="left">

<figure><img src="https://i.ibb.co/dfD1rc7/start.png" alt=""><figcaption></figcaption></figure>

</div>

***

## QRCode

With the QRCode capability, players can enter the website via mobile. Activate this feature by running the command `/melodymine start qrcode`, which generates a QRCode.&#x20;

Players can scan this code with their mobile devices to automatically join the voice chat.

<div align="left">

<figure><img src="https://i.ibb.co/y5MntSP/qrcode.png" alt=""><figcaption></figcaption></figure>

</div>

***

## Call System

This feature allow players to initiate voice calls with other online players using the command `/melodymine call start <player>`.

&#x20;The call system resembles real-life conversations and facilitates genuine interaction between players.

<div align="left">

<figure><img src="https://i.ibb.co/pyjTX8N/callpng.png" alt=""><figcaption></figcaption></figure>

</div>

***

## 3D Sound

In the MelodyMine voice chat, sound is rendered in 3D, providing an immersive experience where players can accurately locate the source of sounds based on the speaker's position.&#x20;

You can enable or disable this feature and adjust the 3D sound model within the voice chat.

<div align="left">

<figure><img src="../.gitbook/assets/Screenshot 2024-05-13 093727.png" alt=""><figcaption></figcaption></figure>

</div>

***

## Talk NamTag and BossBar

When you engage in voice chat on the Minecraft server, a boss bar appears above your character, while other players see a nametag above your character's head.&#x20;

{% hint style="info" %}
You can fully customize both the boss bar and nametag, even using Minecraft items or custom items, via the `talk.yml` file in the plugin folder.
{% endhint %}

<div align="left">

<figure><img src="https://i.ibb.co/sQV9PyL/nametag-bossbar.png" alt=""><figcaption></figcaption></figure>

</div>

***

## Force Voice

You can enforce voice chat for players, ensuring that it is enabled for gameplay on the server.&#x20;

{% hint style="info" %}
Configuration settings related to forced voice can be found in the `settings.yml` file within the plugin folder.
{% endhint %}

***

## Shortcut

Players can mute themselves by pressing Shift + F on the website. If they've muted themselves, they can also unmute using the same shortcut.

{% hint style="info" %}
&#x20;Configuration settings for this feature can be adjusted in the `settings.yml` file within the plugin folder.
{% endhint %}

## Disable worlds

You can disable voice chat in specific worlds using this feature.

{% hint style="info" %}
&#x20;Configuration settings for disabling worlds can be found in the `settings.yml` file within the plugin folder.
{% endhint %}

***

## Sound and Music

With MelodyMine, you can play sounds for players during various moments. To utilize this capability, you need to integrate with the API provided for sounds.&#x20;

For more information, you can delve into the Sound API documentation.

{% content-ref url="../api/sounds.md" %}
[sounds.md](../api/sounds.md)
{% endcontent-ref %}
