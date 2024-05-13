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

# PostStartCallEvent

{% hint style="info" %}
The `PostStartCallEvent` is a custom event in the MelodyMine plugin that is called after a call has been started between two players. This event provides access to the `MelodyPlayer` instances of the two players involved in the call.
{% endhint %}

#### Event Details

<table><thead><tr><th width="178">Field</th><th width="171">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who initiated the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is the target of the call.</td></tr></tbody></table>

#### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostStartCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPostStartCall(PostStartCallEvent event) {
        // Get the players involved in the call
        MelodyPlayer melodyPlayer = event.getMelodyPlayer();
        MelodyPlayer targetPlayer = event.getTargetPlayer();

        // Log the event to the console
        Bukkit.getLogger().info(melodyPlayer.getName() + " has started a call with " + targetPlayer.getName());
    }
}
```

In this example, the `onPostStartCall` method is annotated with `@EventHandler`, which means it will be called whenever a `PostStartCallEvent` occurs. Inside the method, we retrieve the `MelodyPlayer` instances of the two players involved in the call and log a message to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for it to work.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(), this);
}
```

This will ensure that the `ExampleListener` class is listening for events.
