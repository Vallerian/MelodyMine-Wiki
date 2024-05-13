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

# PreDenyCallEvent

{% hint style="info" %}
The `PreDenyCallEvent` is a custom event in the Bukkit API that is called before a call is denied in the MelodyMine plugin. This event provides information about the player who is denying the call (`melodyPlayer`) and the target player whose call is being denied (`targetPlayer`).
{% endhint %}

### Event Details

<table><thead><tr><th width="202">Attribute</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td>The player who is denying the call.</td></tr><tr><td><code>targetPlayer</code></td><td>The player whose call is being denied.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreDenyCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPreDenyCall(PreDenyCallEvent event) {
        plugin.getLogger().info(event.getMelodyPlayer().getName() + " is denying a call from " + event.getTargetPlayer().getName());

        // If the event is cancellable and you want to cancel it based on some condition
        // event.setCancelled(true);

        // If the event has a canSendMessage method and you want to prevent the message
        // event.setCanSendMessage(false);
    }
}
```

In this example, when a player denies a call, a message is logged in the console indicating who is denying the call and from whom the call is being denied. If the event is cancellable, you can cancel it based on some condition. Similarly, if the event has a `canSendMessage` method, you can prevent the message from being sent.

{% hint style="warning" %}
Remember to register your event listener in the `onEnable` method of your main plugin class.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
}
```

This will ensure that your listener is active and can respond to the `PreDenyCallEvent`.
