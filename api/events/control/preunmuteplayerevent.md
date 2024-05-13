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

# PreUnMutePlayerEvent

{% hint style="info" %}
The `PreUnMutePlayerEvent` is a custom event in the MelodyMine plugin that is called before a player is server unmuted. This event is cancellable, meaning that you can prevent the player from being unmuted by cancelling this event in your event handler.
{% endhint %}

### Class Structure

<table><thead><tr><th width="187">Method/Value</th><th width="163">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is about to be unmuted.</td></tr><tr><td><code>isCancelled</code></td><td><code>boolean</code></td><td>Whether the event is cancelled. If true, the player will not be unmuted.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreUnMutePlayerEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPreUnMutePlayer(PreUnMutePlayerEvent event) {
        // Get the player who is about to be unmuted
        MelodyPlayer player = event.getMelodyPlayer();

        // Print a message to the console
        Bukkit.getLogger().info(player.getName() + " is about to be unmuted!");

        // Cancel the event if the player's name is "TAHER7", preventing them from being unmuted
        if (player.getName().equals("TAHER7")) {
            event.setCancelled(true);
            Bukkit.getLogger().info("Cancelled unmute event for Steve");
        }
    }
}
```

{% hint style="warning" %}
Remember to register your event listener with the Bukkit plugin manager in your plugin's `onEnable` method for your listener to function.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyListener(), this);
}
```

This example listens for the `PreUnMutePlayerEvent`, logs a message to the console when the event is triggered, and cancels the event if the player's name is "TAHER7", preventing them from being unmuted.
