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

# PostToggleCallEvent

{% hint style="info" %}
The `PostToggleCallEvent` is a custom event in the MelodyMine plugin. This event is triggered after a player toggles their call status. It provides information about the player who toggled their call status.
{% endhint %}

### Event Details

<table><thead><tr><th width="174">Attribute</th><th width="182">Type</th><th>Description</th></tr></thead><tbody><tr><td>melodyPlayer</td><td>MelodyPlayer</td><td>The player who toggled their call status.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PostToggleCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPostToggleCall(PostToggleCallEvent event) {
        // Get the player who toggled their call status
        MelodyPlayer player = event.getMelodyPlayer();

        // Print a message to the console
        Bukkit.getLogger().info(player.getName() + " has toggled their call status.");
    }
}
```

In this example, we create a listener for the `PostToggleCallEvent`. When the event is triggered, we retrieve the `MelodyPlayer` who toggled their call status and print a message to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method for it to work.
{% endhint %}
