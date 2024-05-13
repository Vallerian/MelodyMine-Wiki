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

# PreDisableAdminModeEvent

{% hint style="info" %}
The `PreDisableAdminModeEvent` is a custom event in the Bukkit API that is called before an admin mode is disabled for a `MelodyPlayer`.
{% endhint %}

This event is cancellable, which means you can prevent the admin mode from being disabled by cancelling this event in your event handler.

### Event Details

<table><thead><tr><th width="252">Attribute</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td>The <code>MelodyPlayer</code> instance for which the admin mode is about to be disabled.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event and use its properties:

```java
import ir.taher7.melodymine.api.events.PreDisableAdminModeEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPreDisableAdminMode(PreDisableAdminModeEvent event) {
        // Get the MelodyPlayer instance
        MelodyPlayer player = event.getMelodyPlayer();

        // Check if the event is cancellable
        if (event.isCancellable()) {
            // Cancel the event
            event.setCancelled(true);

            // Log to console
            Bukkit.getLogger().info("Admin mode disable attempt for player " + player.getName() + " has been cancelled.");
        }
    }
}
```

In this example, we're listening for the `PreDisableAdminModeEvent`. If the event is cancellable, we cancel it and log a message to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method to ensure that your event handler is called when the event is fired.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyListener(), this);
}
```

This will ensure that your `MyListener` class is listening for events.
