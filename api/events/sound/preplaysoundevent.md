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

# PrePlaySoundEvent

{% hint style="info" %}
The `PrePlaySoundEvent` is a custom event in the MelodyMine plugin. This event is triggered before a sound is played in the client for players. It provides information about the sound that is about to be played, such as the sound name, whether the sound is sent to all players, the socket ID of the player who will receive the sound, and the volume of the sound.
{% endhint %}

### Event Details

<table><thead><tr><th width="191">Property</th><th width="155">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td><code>String</code></td><td>The name of the sound that is about to be played.</td></tr><tr><td><code>sendToAll</code></td><td><code>Boolean</code></td><td>Indicates whether the sound is sent to all players.</td></tr><tr><td><code>socketID</code></td><td><code>String</code></td><td>The socket ID of the player who will receive the sound.</td></tr><tr><td><code>volume</code></td><td><code>Double</code></td><td>The volume of the sound.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PrePlaySoundEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPrePlaySound(PrePlaySoundEvent event) {
        String soundName = event.getSoundName();
        boolean sendToAll = event.isSendToAll();
        String socketID = event.getSocketID();
        Double volume = event.getVolume();

        plugin.getLogger().info("A sound is about to be played!");
        plugin.getLogger().info("Sound Name: " + soundName);
        plugin.getLogger().info("Send to All: " + sendToAll);
        plugin.getLogger().info("Socket ID: " + socketID);
        plugin.getLogger().info("Volume: " + volume);
    }
}
```

In this example, we create a listener for the `PrePlaySoundEvent`. When the event is triggered, we retrieve the details of the sound that is about to be played and log them to the console.

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable` method to ensure that it listens to the events.
{% endhint %}
