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

# PostEndCallEvent

{% hint style="info" %}
The `PostEndCallEvent` is a custom event in the MelodyMine plugin that is triggered after a voice call between two players has ended. This event provides information about the two players involved in the call.
{% endhint %}

### Event Details

<table><thead><tr><th width="188">Field</th><th width="162">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who was in the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The other player who was in the call.</td></tr></tbody></table>

### Event Usage

You can listen to this event in your plugin and perform actions based on the event details. Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostEndCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyPluginListener implements Listener {

    @EventHandler
    public void onPostEndCall(PostEndCallEvent event) {
        // Get the players involved in the call
        MelodyPlayer melodyPlayer = event.getMelodyPlayer();
        MelodyPlayer targetPlayer = event.getTargetPlayer();

    }
}
```

In this example, we're listening for the `PostEndCallEvent` and when it's triggered, we're logging the names of the players who were in the call to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for it to work.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyPluginListener(), this);
}
```
