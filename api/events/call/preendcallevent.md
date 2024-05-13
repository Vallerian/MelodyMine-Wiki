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

# PreEndCallEvent

{% hint style="info" %}
The `PreEndCallEvent` is a custom event in the Bukkit API that is called before a call between two players is ended. This event is cancellable, which means you can prevent the call from ending based on your custom logic. It also allows you to control whether a message is sent to the players involved in the call.
{% endhint %}

### Class Structure

<table><thead><tr><th width="269">Method/Variable</th><th width="173">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is in the call that is about to end.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The other player involved in the call.</td></tr><tr><td><code>isCancelled()</code></td><td><code>boolean</code></td><td>Checks if the event is cancelled.</td></tr><tr><td><code>setCancelled(boolean)</code></td><td><code>void</code></td><td>Sets the cancellation state of the event.</td></tr><tr><td><code>canSendMessage</code></td><td><code>boolean</code></td><td>Determines whether a message can be sent to the players involved in the call.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreEndCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPreEndCall(PreEndCallEvent event) {
        // Access the players involved in the call
        MelodyPlayer player1 = event.getMelodyPlayer();
        MelodyPlayer player2 = event.getTargetPlayer();

        // Print their names to the console
        Bukkit.getLogger().info(player1.getName() + " and " + player2.getName() + " are about to end their call.");

        // If a certain condition is met, cancel the event
        if (someCondition) {
            event.setCancelled(true);
            Bukkit.getLogger().info("The call between " + player1.getName() + " and " + player2.getName() + " was prevented from ending.");
        }

        // If another condition is met, prevent the message from being sent
        if (anotherCondition) {
            event.setCanSendMessage(false);
            Bukkit.getLogger().info("No message will be sent to " + player1.getName() + " and " + player2.getName() + " about the call ending.");
        }
    }
}
```

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method for it to work.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyListener(), this);
}
```
