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

# PreAcceptCallEvent

{% hint style="info" %}
The `PreAcceptCallEvent` is a custom event in the Bukkit API. It is triggered when a player accepts a call request in the MelodyMine plugin. This event is called before the call is officially accepted, hence the "Pre" in its name. This gives developers an opportunity to add custom logic or conditions before the call is accepted.
{% endhint %}

### Event Details

<table><thead><tr><th width="246">Attribute</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td>The <code>MelodyPlayer</code> instance of the player who is accepting the call.</td></tr><tr><td><code>targetPlayer</code></td><td>The <code>MelodyPlayer</code> instance of the player who initiated the call.</td></tr><tr><td><code>isCancelled</code></td><td>A boolean value indicating whether the event is cancelled. If true, the call acceptance process will not proceed. This attribute is mutable.</td></tr><tr><td><code>canSendMessage</code></td><td>A boolean value indicating whether a message can be sent to the player. This attribute is mutable.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PreAcceptCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin implements Listener {

    @Override
    public void onEnable() {
        getServer().getPluginManager().registerEvents(this, this);
    }

    @EventHandler
    public void onPreAcceptCall(PreAcceptCallEvent event) {
        // Access the MelodyPlayer instances
        MelodyPlayer melodyPlayer = event.getMelodyPlayer();
        MelodyPlayer targetPlayer = event.getTargetPlayer();

        // Print to console
        getLogger().info(melodyPlayer.getName() + " is accepting a call from " + targetPlayer.getName());

        // Cancel the event if needed
        if (someCondition) {
            event.setCancelled(true);
            getLogger().info("Call acceptance cancelled due to some condition.");
        }

        // Prevent sending a message to the player
        if (anotherCondition) {
            event.setCanSendMessage(false);
            getLogger().info("Prevented sending a message to the player.");
        }
    }
}
```

In this example, we're listening for the `PreAcceptCallEvent`, and when it's triggered, we're logging the names of the players involved in the call. We also have the ability to cancel the event or prevent a message from being sent to the player based on certain conditions.

{% hint style="warning" %}
Remember to replace `someCondition` and `anotherCondition` with your own logic.
{% endhint %}
