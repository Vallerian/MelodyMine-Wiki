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

# PostPlayerSetDeafenEvent

{% hint style="info" %}
The `PostPlayerSetDeafenEvent` is a custom event in the MelodyMine plugin. This event is triggered after a player's deafen status has been set. This could be either enabling or disabling the deafen status.
{% endhint %}

### Event Details

<table><thead><tr><th width="186">Field</th><th width="193">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player whose deafen status has been set.</td></tr><tr><td><code>value</code></td><td><code>boolean</code></td><td>The new deafen status of the player. <code>false</code>if the player is now deafened, <code>true</code>otherwise.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostPlayerSetDeafenEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPlayerSetDeafen(PostPlayerSetDeafenEvent event) {
        // Get the player and the new deafen status
        MelodyPlayer player = event.getMelodyPlayer();
        boolean isDeafened = event.getValue();

        // Log the new deafen status to the console
        Bukkit.getLogger().info(player.getName() + " is now " + (isDeafened ? "not deafened" : "deafened"));
    }
}
```

In this example, we create a listener for the `PostPlayerSetDeafenEvent`. When the event is triggered, we retrieve the player and their new deafen status. We then log this information to the console.

{% hint style="warning" %}
Remember to register your event listener with the Bukkit plugin manager for your listener to receive events.
{% endhint %}
