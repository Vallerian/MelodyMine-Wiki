# 🔊 Sounds

## MelodyMine Sounds API

To use the MelodyMine Sound API, you need to navigate to the path `web/client/src/` within the MelodyMine website and open the file `sounds.ts`.&#x20;

In this file you will find a list of JSON objects representing different sounds.

```typescript
export default [
    {
        name: "notification",
        url: "sound/notif-sound.mp3",
        loop: false,
        volume: 0.5
    },
    {
        name: "calling",
        url: "sound/calling-sound.mp3",
        loop: false,
        volume: 0.5
    },
    {
        name: "calling2",
        url: "sound/calling-sound_2.mp3",
        loop: false,
        volume: 0.5
    },
    {
        name: "hangUp",
        url: "sound/hang-up-sound.mp3",
        loop: false,
        volume: 0.5
    },
    {
        name: "radio",
        url: "http://stream.laut.fm/pop-musik",
        loop: false,
        volume: 0.1
    },
]
```

To add a new sound to the client, you simply need to follow a similar procedure to the example provided below:

```typescript
{
   name: string,      // Name must be unique.
   url: string,       // Sound URL local or stream.
   loop: boolean,     // Loop for local sounds.
   volume: number     // Sound volume between 0 / 1.
}
```

{% hint style="info" %}
If you prefer to keep the sound files locally, you can place your sound files in the directory `web/client/public/sound`, and then reference them in the `sounds.ts` file using URLs like `sound/sound-name.mp3`.\


If you wish to utilize radio streams, you can directly provide the stream link in the `url` field of the sound object in the `sounds.ts` file.
{% endhint %}

{% hint style="info" %}
Please note that when you make changes to the `sounds.ts` file or any other file in the client, to initialize all the files and update the client for players to be able to play sounds, you need to rebuild the Docker image and remove the Docker volume for the client to clear caches.\


To perform this task, follow these commands in sequence after navigating to the directory `web/docker`:

```bash
sudo sh stop.sh
sudo docker rm client
sudo docker rmi docker-client
sudo sh start.sh
```
{% endhint %}

***

### Sound Events and Managers

You can create and utilize events and sound managers within MelodyMine to handle various functionalities related to sounds.&#x20;

By navigating to the Sounds Events and Sounds Manager pages in the MelodyMine plugin, you can explore examples of how sound is used within the plugin.\


Events

{% content-ref url="events/sound/" %}
[sound](events/sound/)
{% endcontent-ref %}

***

Managers

{% content-ref url="melodymanager/sound/" %}
[sound](melodymanager/sound/)
{% endcontent-ref %}
