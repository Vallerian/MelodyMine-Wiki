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

# PreStopSoundEvent

{% hint style="info" %}
The `PreStopSoundEvent` is a custom event class in the MelodyMine plugin. This event is triggered before a sound is stopped in the client. It provides information about the sound that is about to be stopped, whether the sound is being sent to all players, and the socket ID of the player who initiated the stop sound action.
{% endhint %}

### Class Properties

<table><thead><tr><th width="156">Property</th><th width="115">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td>String</td><td>The name of the sound that is about to be stopped.</td></tr><tr><td><code>sendToAll</code></td><td>Boolean</td><td>Indicates whether the sound is being sent to all players.</td></tr><tr><td><code>socketID</code></td><td>String?</td><td>The socket ID of the player who initiated the stop sound action. This could be null.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PreStopSoundEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPreStopSound(PreStopSoundEvent event) {
        String soundName = event.getSoundName();
        boolean sendToAll = event.isSendToAll();
        String socketID = event.getSocketID();

        plugin.getLogger().info("A sound stop event has been triggered!");
        plugin.getLogger().info("Sound Name: " + soundName);
        plugin.getLogger().info("Send to All: " + sendToAll);
        plugin.getLogger().info("Socket ID: " + (socketID != null ? socketID : "N/A"));
    }
}
```

In this example, we create a listener for the `PreStopSoundEvent`. When the event is triggered, we retrieve the sound name, whether the sound is being sent to all players, and the socket ID of the player who initiated the stop sound action. We then log this information to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for it to work correctly.
{% endhint %}
