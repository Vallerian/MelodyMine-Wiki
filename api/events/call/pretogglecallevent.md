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

# PreToggleCallEvent

{% hint style="info" %}
The `PreToggleCallEvent` is a custom event in the MelodyMine plugin. It is triggered before a player toggles their call status. This event allows developers to interact with the plugin's functionality, providing a way to execute custom code before the call status of a player is toggled.
{% endhint %}

### Event Details

<table><thead><tr><th width="208">Attribute</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td>The <code>MelodyPlayer</code> instance representing the player who is about to toggle their call status.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreToggleCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPreToggleCall(PreToggleCallEvent event) {
        // Get the MelodyPlayer instance
        MelodyPlayer player = event.getMelodyPlayer();

        // Access the Bukkit logger and print the player's name
        Bukkit.getLogger().info(player.getName() + " is about to toggle their call status.");
    }
}
```

In this example, we create a listener for the `PreToggleCallEvent`. When the event is triggered, we retrieve the `MelodyPlayer` instance from the event and print a message to the console using Bukkit's logger.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method to ensure that it listens to the event correctly.
{% endhint %}
