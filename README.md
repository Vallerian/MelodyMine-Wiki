---
description: Welcome to the MelodyMine Documentation
---

# 🎵 Introduction

<figure><img src=".gitbook/assets/melody-logo (1).png" alt=""><figcaption></figcaption></figure>

## What is MelodyMine ?

MelodyMine is an [open-source](https://github.com/Vallerian/MelodyMine) voice chat plugin without the need any mod for Minecraft servers, facilitating voice communication directly from the browser.\


***

## How MelodyMine Works ?

The entire MelodyMine system consists of three components: the Minecraft Plugin, the Websocket Server, and the Next.js Server.\
\
These components establish connections via websockets, where data is transmitted from the plugin to the websocket server.The websocket server identifies which data needs to be sent for individual checks on the Next.js server.\
\
Finally, the Next.js server communicates with the client, utilizing data received from the websocket via the plugin, to maintain voice communication among online players in the voice chat.\


{% content-ref url="guide/installation.md" %}
[installation.md](guide/installation.md)
{% endcontent-ref %}

{% content-ref url="guide/features.md" %}
[features.md](guide/features.md)
{% endcontent-ref %}

***

## How can I use MelodyMine?

To utilize MelodyMine, players simply need to join the server,\
and use the command `/melodymine start link` to receive a link for client entry.&#x20;

Clicking on this link redirects them to the website without any additional requirements. It's just a matter of being near a player online to hear their voice.

Also, if you prefer, you can enter the voice chat via your phone by using&#x20;

the command `/melodymine start qrcode`, which will generate a QR code. After scanning it, you'll be able to join the voice chat.\


{% hint style="success" %}
**MelodyMine Demo**\
\
Website **:** [MelodyMine.TAHER7.iR](https://melodymine.taher7.ir/)

Server  IP**:** `Play.TAHER7.IR`
{% endhint %}

{% content-ref url="essentials/commands.md" %}
[commands.md](essentials/commands.md)
{% endcontent-ref %}

{% content-ref url="essentials/permissions.md" %}
[permissions.md](essentials/permissions.md)
{% endcontent-ref %}

***

## Why should I use MelodyMine?

The capabilities of MelodyMine don't end here! MelodyMine offers personalized features for players, a comprehensive API, and complete support with examples for developers to create their own essential additions.\
\
Currently, many servers and players are using MelodyMine, which indicates their satisfaction with its basic functionalities on their servers.

<figure><img src="https://bstats.org/signatures/bukkit/MelodyMine.svg" alt=""><figcaption></figcaption></figure>

{% content-ref url="api/plugin-usage.md" %}
[plugin-usage.md](api/plugin-usage.md)
{% endcontent-ref %}

{% content-ref url="essentials/placeholders.md" %}
[placeholders.md](essentials/placeholders.md)
{% endcontent-ref %}
