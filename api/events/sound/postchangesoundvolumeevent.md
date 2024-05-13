---
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: false
  pagination:
    visible: true
---

# PostChangeSoundVolumeEvent

{% hint style="info" %}
The `PostChangeSoundVolumeEvent` is a custom event in the Bukkit API. It is triggered after the volume of a sound is changed in the MelodyMine plugin. This event provides information about the sound that had its volume changed, whether the change should be sent to all players, the socket ID, and the new volume level.
{% endhint %}

### Event Details

<table><thead><tr><th width="196">Property</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td>The name of the sound that had its volume changed.</td></tr><tr><td><code>sendToAll</code></td><td>A boolean indicating whether the volume change should be sent to all players.</td></tr><tr><td><code>socketID</code></td><td>The socket ID associated with the event.</td></tr><tr><td><code>volume</code></td><td>The new volume level of the sound.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostChangeSoundVolumeEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class VolumeChangeListener implements Listener {

    @EventHandler
    public void onVolumeChange(PostChangeSoundVolumeEvent event) {
        // Get the Bukkit logger
        Logger logger = Bukkit.getLogger();

        // Log the details of the event
        logger.info("Sound volume changed:");
        logger.info("Sound Name: " + event.getSoundName());
        logger.info("Send to All: " + event.isSendToAll());
        logger.info("Socket ID: " + event.getSocketID());
        logger.info("New Volume: " + event.getVolume());
    }
}
```

In this example, we create a listener for the `PostChangeSoundVolumeEvent`. When the event is triggered, we log the details of the event to the console using Bukkit's logger.

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable` method to ensure that it listens to the event.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new VolumeChangeListener(), this);
}
```

This will ensure that the `VolumeChangeListener` starts listening for the `PostChangeSoundVolumeEvent` when your plugin is enabled.
