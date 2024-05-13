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

# PreSetVolumeEvent

{% hint style="info" %}
The `PreSetVolumeEvent` is a custom event in the MelodyMine plugin. This event is triggered before the volume of a player is set. It provides the ability to get the player and target player involved in the volume setting process.
{% endhint %}

### Event Details

<table><thead><tr><th width="252">Method</th><th>Description</th></tr></thead><tbody><tr><td><code>getPlayer()</code></td><td>Returns the <code>MelodyPlayer</code> instance of the player whose volume is being set.</td></tr><tr><td><code>getTargetPlayer()</code></td><td>Returns the <code>MelodyPlayer</code> instance of the target player involved in the volume setting process.</td></tr></tbody></table>

### Event Usage

{% hint style="warning" %}
This event can be used to perform actions or checks before the volume of a player is set. For example, you can use it to log the volume setting process or prevent it under certain conditions.
{% endhint %}

### Example

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreSetVolumeEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class VolumeListener implements Listener {

    @EventHandler
    public void onPreSetVolume(PreSetVolumeEvent event) {
        // Get the player and target player
        MelodyPlayer player = event.getPlayer();
        MelodyPlayer targetPlayer = event.getTargetPlayer();

        // Log the volume setting process
        Bukkit.getLogger().info("Setting volume for player: " + player.getName());
        Bukkit.getLogger().info("Target player: " + targetPlayer.getName());
    }
}
```

In this example, we create a listener for the `PreSetVolumeEvent`. When the event is triggered, we retrieve the player and target player involved in the volume setting process and log their names to the console.
