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

# PreStartCallEvent

{% hint style="info" %}
The `PreStartCallEvent` is a custom event in the MelodyMine plugin. It is triggered before a call is started between two players. This event provides the ability to interact with the call process, allowing developers to add custom logic or modify the behavior of the call initiation process.
{% endhint %}

### Event Details

<table><thead><tr><th width="202">Property</th><th width="163">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is initiating the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is the target of the call.</td></tr><tr><td><code>canSendMessage</code></td><td><code>boolean</code></td><td>A flag indicating whether a message can be sent to the players involved in the call.</td></tr><tr><td><code>isCancelled</code></td><td><code>boolean</code></td><td>A flag indicating whether the event is cancelled. If true, the call will not be initiated.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreStartCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class CustomListener implements Listener {

    @EventHandler
    public void onPreStartCall(PreStartCallEvent event) {
        // Access the MelodyPlayer objects
        MelodyPlayer melodyPlayer = event.getMelodyPlayer();
        MelodyPlayer targetPlayer = event.getTargetPlayer();

        // Print to console
        Bukkit.getLogger().info(melodyPlayer.getName() + " is initiating a call with " + targetPlayer.getName());

        // Check if a message can be sent
        if (event.canSendMessage()) {
            // Add custom logic here
        }

        // Cancel the event
        // event.setCancelled(true);
    }
}
```

In this example, we're listening for the `PreStartCallEvent`. When the event is triggered, we're logging the names of the players involved in the call to the console. We also check if a message can be sent during this event. If the event is cancelled, the call will not be initiated.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method to ensure that it is active.
{% endhint %}
