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

# PrePlayerSetDeafenEvent

{% hint style="info" %}
The `PrePlayerSetDeafenEvent` is a custom event in the MelodyMine plugin. This event is triggered before a player's deafen status is set. It provides information about the player and the new deafen status.
{% endhint %}

### Event Details

<table><thead><tr><th width="180">Field</th><th width="197">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player whose deafen status is being set.</td></tr><tr><td><code>value</code></td><td><code>boolean</code></td><td>The new deafen status.</td></tr></tbody></table>

### Event Usage

This event can be used to perform actions before a player's deafen status is set. For example, you can use it to log the change in deafen status or to prevent the deafen status from being set under certain conditions.

### Example

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PrePlayerSetDeafenEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class DeafenStatusListener implements Listener {

    @EventHandler
    public void onPlayerSetDeafen(PrePlayerSetDeafenEvent event) {
        // Get the player and the new deafen status
        MelodyPlayer player = event.getMelodyPlayer();
        boolean isDeafened = event.getValue();

        // Log the change in deafen status
        Bukkit.getLogger().info(player.getName() + " is about to be set to " + (isDeafened ? "deafened" : "not deafened"));

        // Prevent the deafen status from being set if the player is an admin
        if (player.isAdmin()) {
            event.setCancelled(true);
            Bukkit.getLogger().info("Cancelled deafen status change for admin player " + player.getName());
        }
    }
}
```

In this example, the `onPlayerSetDeafen` method is called when the `PrePlayerSetDeafenEvent` is triggered. The method logs the player's name and the new deafen status. If the player is an admin, the method cancels the event to prevent the deafen status from being set.

{% hint style="warning" %}
Remember to register your event listener with the Bukkit plugin manager to ensure that your `onPlayerSetDeafen` method is called when the event is triggered.
{% endhint %}
