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

# PostSetVolumeEvent

{% hint style="info" %}
The `PostSetVolumeEvent` is a custom event in the MelodyMine plugin. This event is triggered after the volume of a player is set. It provides information about the player whose volume was set and the target player who set the volume.
{% endhint %}

### Event Details

<table><thead><tr><th width="215">Field</th><th width="153">Type</th><th>Description</th></tr></thead><tbody><tr><td>playerUuid</td><td>String</td><td>The UUID of the player whose volume was set.</td></tr><tr><td>targetSocketID</td><td>String</td><td>The socket ID of the target player who set the volume.</td></tr></tbody></table>

### Methods

<table><thead><tr><th width="206">Method</th><th width="159">Return Type</th><th>Description</th></tr></thead><tbody><tr><td>getPlayer()</td><td>MelodyPlayer</td><td>Returns the <code>MelodyPlayer</code> instance of the player whose volume was set.</td></tr><tr><td>getTargetPlayer()</td><td>MelodyPlayer</td><td>Returns the <code>MelodyPlayer</code> instance of the target player who set the volume.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostSetVolumeEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class VolumeListener implements Listener {

    @EventHandler
    public void onVolumeSet(PostSetVolumeEvent event) {
        // Get the player who had their volume set
        MelodyPlayer player = event.getPlayer();

        // Get the target player who set the volume
        MelodyPlayer targetPlayer = event.getTargetPlayer();

        // Log the event to the console
        Bukkit.getLogger().info(targetPlayer.getName() + " set the volume for " + player.getName());
    }
}
```

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable()` method to ensure that it is active.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new VolumeListener(), this);
}
```

This example will print a message to the console whenever a player's volume is set, indicating who set the volume and for whom.
