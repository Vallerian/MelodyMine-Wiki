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

# PostAcceptCallEvent

{% hint style="info" %}
The `PostAcceptCallEvent` is a custom event in the Bukkit API that is triggered after a player accepts a call request in the MelodyMine plugin. This event provides information about the player who accepted the call and the player who initiated the call.
{% endhint %}

### Event Details

<table><thead><tr><th width="181">Property</th><th width="157">Type</th><th>Description</th></tr></thead><tbody><tr><td>melodyPlayer</td><td>MelodyPlayer</td><td>The player who accepted the call request.</td></tr><tr><td>targetPlayer</td><td>MelodyPlayer</td><td>The player who initiated the call request.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostAcceptCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPostAcceptCall(PostAcceptCallEvent event) {
        String acceptorName = event.getMelodyPlayer().getName();
        String initiatorName = event.getTargetPlayer().getName();

        plugin.getLogger().info(acceptorName + " has accepted a call from " + initiatorName);
    }
}
```

In this example, we create a listener for the `PostAcceptCallEvent`. When the event is triggered, we retrieve the names of the player who accepted the call and the player who initiated the call. We then log this information to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for it to work correctly.
{% endhint %}
