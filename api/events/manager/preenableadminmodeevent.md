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

# PreEnableAdminModeEvent

{% hint style="info" %}
The `PreEnableAdminModeEvent` is a custom event in the Bukkit API that is called before a player's admin mode is enabled in the MelodyMine plugin. This event is cancellable, which means you can prevent the admin mode from being enabled based on certain conditions in your plugin.
{% endhint %}

### Event Details

<table><thead><tr><th width="233">Property</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td>The <code>MelodyPlayer</code> instance representing the player for whom the admin mode is about to be enabled.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event in a Bukkit plugin:

```java
import ir.taher7.melodymine.api.events.PreEnableAdminModeEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyPluginListener implements Listener {

    @EventHandler
    public void onPreEnableAdminMode(PreEnableAdminModeEvent event) {
        // Access the MelodyPlayer instance
        MelodyPlayer player = event.getMelodyPlayer();

        // Print the player's name to the console
        Bukkit.getLogger().info("Admin mode is about to be enabled for: " + player.getName());

        // Cancel the event based on a condition
        if (player.getName().equals("NotAdmin")) {
            event.setCancelled(true);
            Bukkit.getLogger().info("Cancelled admin mode for: " + player.getName());
        }
    }
}
```

In this example, we're listening for the `PreEnableAdminModeEvent`. When the event is triggered, we log the name of the player for whom the admin mode is about to be enabled. If the player's name is "NotAdmin", we cancel the event to prevent the admin mode from being enabled for this player.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method to ensure that your plugin listens for the `PreEnableAdminModeEvent`.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyPluginListener(), this);
}
```
