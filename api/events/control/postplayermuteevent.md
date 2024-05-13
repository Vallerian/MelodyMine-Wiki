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

# PostPlayerMuteEvent

{% hint style="info" %}
The `PostPlayerMuteEvent` is a custom event in the Bukkit API that is called after a player's server mute status has been changed.
{% endhint %}

### Class Structure

<table><thead><tr><th width="244">Method</th><th width="182">Return Type</th><th>Description</th></tr></thead><tbody><tr><td><code>getMelodyPlayer()</code></td><td><code>MelodyPlayer</code></td><td>Returns the <code>MelodyPlayer</code> instance associated with this event.</td></tr></tbody></table>

### Usage

To listen to this event, you need to create a class that implements the `Listener` interface and use the `@EventHandler` annotation to mark a method that will be called when the event is triggered.

Here is an example of how to listen to the `PostPlayerMuteEvent`:

```java
import ir.taher7.melodymine.api.events.PostPlayerMuteEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPlayerMute(PostPlayerMuteEvent event) {
        MelodyPlayer player = event.getMelodyPlayer();
        Bukkit.getLogger().info(player.getName() + " has been muted.");
    }
}
```

In this example, when a player's mute status changes, a message is printed to the console with the player's name.

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable()` method to ensure that your listener receives the events.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyListener(), this);
}
```

This will ensure that your `MyListener` class will receive the `PostPlayerMuteEvent` when it is called.
