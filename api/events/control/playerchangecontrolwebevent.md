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

# PlayerChangeControlWebEvent

{% hint style="info" %}
The `PlayerChangeControlWebEvent` is a custom event in the MelodyMine plugin. This event is triggered when a player changes their control settings on the web client. The control settings include the player's mute and deafen status.
{% endhint %}

### Event Details

<table data-full-width="false"><thead><tr><th width="203">Property</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td>The <code>MelodyPlayer</code> instance representing the player who changed their control settings.</td></tr><tr><td><code>control</code></td><td>The <code>MelodyControl</code> instance representing the control settings that were changed.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PlayerChangeControlWebEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private final JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPlayerChangeControlWeb(PlayerChangeControlWebEvent event) {
        String playerName = event.getMelodyPlayer().getName();
        String controlType = event.getControl().getType();
        boolean controlValue = event.getControl().getValue();

        String message = String.format("Player %s changed their %s control to %s", playerName, controlType, controlValue ? "enabled" : "disabled");
        plugin.getLogger().info(message);
    }
}
```

{% hint style="warning" %}
In this example, we're creating a listener for the `PlayerChangeControlWebEvent`. When the event is triggered, we retrieve the player's name, the type of control that was changed, and the new value of the control. We then log this information to the console.
{% endhint %}

Remember to register your listener in your plugin's `onEnable` method:

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
}
```

{% hint style="info" %}
This is a simple example and the actual implementation may vary based on your specific use case.
{% endhint %}
