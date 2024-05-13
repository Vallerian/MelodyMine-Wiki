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

# PostPlayerSetSelfMuteEvent

{% hint style="info" %}
The `PostPlayerSetSelfMuteEvent` is a custom event in the MelodyMine plugin. This event is triggered after a player's self-mute status has been changed. It provides information about the player and the new mute status.
{% endhint %}

### Event Details

<table><thead><tr><th width="197">Attribute</th><th width="205">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player whose self-mute status has been changed.</td></tr><tr><td><code>value</code></td><td><code>boolean</code></td><td>The new self-mute status of the player.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostPlayerSetSelfMuteEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPlayerSetSelfMute(PostPlayerSetSelfMuteEvent event) {
        // Get the player and the new mute status
        MelodyPlayer player = event.getMelodyPlayer();
        boolean isMuted = event.getValue();

        // Log the information to the console
        Bukkit.getLogger().info(player.getName() + " has changed their self-mute status to: " + isMuted);
    }
}
```

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable` method to ensure that it is active.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(), this);
}
```

This listener will log a message to the console every time a player changes their self-mute status.
