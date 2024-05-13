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

# PreEndPendingCallEvent

{% hint style="info" %}
The `PreEndPendingCallEvent` is a custom event in the MelodyMine plugin. This event is triggered before a pending call ends between two players. It provides access to the `MelodyPlayer` instances of both the caller and the receiver.
{% endhint %}

### Event Details

<table><thead><tr><th width="185">Field</th><th width="193">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who initiated the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who was the target of the call.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreEndPendingCallEvent;
import ir.taher7.melodymine.models.MelodyPlayer;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPreEndPendingCall(PreEndPendingCallEvent event) {
        MelodyPlayer caller = event.getMelodyPlayer();
        MelodyPlayer receiver = event.getTargetPlayer();

        plugin.getLogger().info(caller.getName() + " is ending a pending call with " + receiver.getName());
    }
}
```

In this example, we create a listener for the `PreEndPendingCallEvent`. When the event is triggered, we retrieve the `MelodyPlayer` instances of the caller and the receiver. We then log a message to the console indicating that the caller is ending a pending call with the receiver.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method like so:

```java
getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
```
{% endhint %}
