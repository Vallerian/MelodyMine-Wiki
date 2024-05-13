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

# PrePlayerMuteEvent

{% hint style="info" %}
The `PrePlayerMuteEvent` is a custom event in the Bukkit API that is called before a player is muted in the MelodyMine plugin. This event is cancellable, which means you can prevent the player from being muted based on your custom conditions.
{% endhint %}

### Class Structure

<table><thead><tr><th width="190">Method/Variable</th><th width="174">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is about to be muted.</td></tr><tr><td><code>isCancelled</code></td><td><code>boolean</code></td><td>Determines whether the event should be cancelled or not.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event:

```java
import ir.taher7.melodymine.api.events.PrePlayerMuteEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPlayerMute(PrePlayerMuteEvent event) {
        // Get the player who is about to be muted
        MelodyPlayer player = event.getMelodyPlayer();

        // Print the player's name to the console
        Bukkit.getLogger().info(player.getName() + " is about to be muted.");

        // If the player's name is "TAHER7", cancel the event
        if (player.getName().equals("TAHER7")) {
            event.setCancelled(true);
            Bukkit.getLogger().info("Cancelled the mute event for boi-carti.");
        }
    }
}
```

In this example, we're listening for the `PrePlayerMuteEvent`. When the event is triggered, we log the name of the player who is about to be muted. If the player's name is "TAHER7", we cancel the event and log a message to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for the event to be properly handled.
{% endhint %}
