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

# PreChangeSoundVolumeEvent

The `PreChangeSoundVolumeEvent` is a custom event in the MelodyMine plugin. This event is called before the volume of a sound is changed. It provides information about the sound that is about to have its volume changed, including the sound name, whether the change should be sent to all players, the socket ID of the player who initiated the change, and the new volume level.

{% hint style="info" %}
This event is cancellable, meaning you can prevent the volume change from happening by cancelling this event in your event handler.
{% endhint %}

### Event Details

<table><thead><tr><th width="183">Property</th><th width="142">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td><code>String</code></td><td>The name of the sound that is about to have its volume changed.</td></tr><tr><td><code>sendToAll</code></td><td><code>Boolean</code></td><td>Whether the volume change should be sent to all players.</td></tr><tr><td><code>socketID</code></td><td><code>String</code></td><td>The socket ID of the player who initiated the volume change.</td></tr><tr><td><code>volume</code></td><td><code>Double</code></td><td>The new volume level.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PreChangeSoundVolumeEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin implements Listener {

    @Override
    public void onEnable() {
        getServer().getPluginManager().registerEvents(this, this);
    }

    @EventHandler
    public void onPreChangeSoundVolume(PreChangeSoundVolumeEvent event) {
        // Log the sound name and new volume to the console
        getLogger().info("Sound " + event.getSoundName() + " is about to have its volume changed to " + event.getVolume());
        r
        // Log the details of the event
        logger.info("Sound Name: " + event.getSoundName());
        logger.info("Send To All: " + event.isSendToAll());
        logger.info("Socket ID: " + event.getSocketID());
        logger.info("New Volume: " + event.getVolume());

        // If the volume is above a certain level, cancel the event
        if (event.getVolume() > 1.0) {
            event.setCancelled(true);
            getLogger().info("Cancelled the volume change because the new volume is too high.");
        }
    }
}
```

In this example, we're logging the name of the sound and the new volume to the console whenever a sound's volume is about to be changed. If the new volume is above a certain level, we cancel the event to prevent the volume change from happening.
