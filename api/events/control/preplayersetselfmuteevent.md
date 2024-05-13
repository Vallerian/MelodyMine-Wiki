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

# PrePlayerSetSelfMuteEvent

{% hint style="info" %}
The `PrePlayerSetSelfMuteEvent` is a custom event in the MelodyMine plugin. It is triggered before a player's self-mute status is changed. This event provides information about the player and the new mute status.
{% endhint %}

### Event Details

<table><thead><tr><th width="186">Field</th><th width="160">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player whose self-mute status is about to change.</td></tr><tr><td><code>value</code></td><td><code>Boolean</code></td><td>The new mute status that will be set for the player.</td></tr></tbody></table>

{% hint style="warning" %}
This event is cancellable. If the event is cancelled, the player's self-mute status will not change.
{% endhint %}

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PrePlayerSetSelfMuteEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPrePlayerSetSelfMute(PrePlayerSetSelfMuteEvent event) {
        // Get the player and the new mute status
        MelodyPlayer player = event.getMelodyPlayer();
        boolean newMuteStatus = event.getValue();

        // Log the information to the console
        plugin.getLogger().info(player.getName() + " is about to change their self-mute status to: " + newMuteStatus);

        // If the new mute status is true, cancel the event
        if (newMuteStatus) {
            event.setCancelled(true);
            plugin.getLogger().info("Cancelled the self-mute status change for " + player.getName());
        }
    }
}
```

In this example, we're logging the player's name and their new mute status to the console. If the new mute status is `true`, we cancel the event and log a message indicating that the status change was cancelled.
