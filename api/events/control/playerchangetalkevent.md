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

# PlayerChangeTalkEvent

{% hint style="info" %}
The `PlayerChangeTalkEvent` is a custom event in the MelodyMine plugin. This event is triggered when a player's talk status changes in the voice chat. It contains information about the player's UUID, the server they are on, and their current talk status.
{% endhint %}

### Event Details

<table><thead><tr><th width="141">Field</th><th width="136">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>uuid</code></td><td><code>String</code></td><td>The UUID of the player whose talk status has changed.</td></tr><tr><td><code>server</code></td><td><code>String</code></td><td>The server that the player is currently on.</td></tr><tr><td><code>isTalk</code></td><td><code>Boolean</code></td><td>The current talk status of the player. <code>true</code> if the player is talking, <code>false</code> otherwise.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PlayerChangeTalkEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPlayerChangeTalk(PlayerChangeTalkEvent event) {
         MelodyPlayer player = event.getMelodyPlayer();
         String server = event.getMelodyTalk().getServer();
         boolean isTalk = event.getMelodyTalk().getIsTalk();
           
         plugin.getLogger().info("Player with UUID: " + player.uuid + " on server: " + server + " has changed their talk status to: " + (isTalk ? "talking" : "not talking"));
    }
}
```

In this example, we create a listener for the `PlayerChangeTalkEvent`. When the event is triggered, we retrieve the player's UUID, the server they are on, and their current talk status. We then log this information to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for it to work correctly.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
}
```

This will ensure that the `onPlayerChangeTalk` method is called whenever a `PlayerChangeTalkEvent` is triggered.
