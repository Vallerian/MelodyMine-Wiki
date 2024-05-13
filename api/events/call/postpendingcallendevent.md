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

# PostPendingCallEndEvent



{% hint style="info" %}
The `PostPendingCallEndEvent` is a custom event in the Bukkit API that is triggered after a pending call between two players has ended. This event provides access to the `MelodyPlayer` instances of both the initiating player and the target player of the call.
{% endhint %}

### Event Details

<table><thead><tr><th width="198">Field</th><th width="186">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who initiated the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who was the target of the call.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostPendingCallEndEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPostPendingCallEnd(PostPendingCallEndEvent event) {
        // Access the MelodyPlayer instances
        MelodyPlayer initiator = event.getMelodyPlayer();
        MelodyPlayer target = event.getTargetPlayer();

    }
}
```

In this example, we create a listener for the `PostPendingCallEndEvent`. When the event is triggered, we retrieve the `MelodyPlayer` instances of the initiating player and the target player.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method like so:

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
}
```
{% endhint %}
