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

# PrePauseSoundEvent

{% hint style="info" %}
The `PrePauseSoundEvent` class is a custom event in the Bukkit API. It is triggered before a sound is paused in the MelodyMine plugin. This event provides information about the sound that is about to be paused, including the sound name, whether the pause should be sent to all players, and the socket ID associated with the event.
{% endhint %}

### Class Properties

<table><thead><tr><th width="177">Property</th><th width="160">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td>String</td><td>The name of the sound that is about to be paused.</td></tr><tr><td><code>sendToAll</code></td><td>Boolean</td><td>Indicates whether the pause event should be sent to all players.</td></tr><tr><td><code>socketID</code></td><td>String?</td><td>The socket ID associated with the event. This could be null.</td></tr></tbody></table>

### Class Methods

<table><thead><tr><th width="199">Method</th><th width="143">Return Type</th><th>Description</th></tr></thead><tbody><tr><td><code>isCancelled</code></td><td>Boolean</td><td>Checks if the event is cancelled.</td></tr><tr><td><code>setCancelled</code></td><td>Void</td><td>Sets the cancellation state of this event. A cancelled event will not be executed in the server, but will still pass to other plugins.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PrePauseSoundEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPrePauseSound(PrePauseSoundEvent event) {
        // Check if the event is cancelled
        if (event.isCancelled()) {
            return;
        }

        // Get the sound name
        String soundName = event.getSoundName();

        // Log the sound name to the console
        Bukkit.getLogger().info("About to pause sound: " + soundName);

        // If the event is set to send to all, log this information
        if (event.isSendToAll()) {
            Bukkit.getLogger().info("The sound pause will be sent to all players.");
        }

        // Get the socket ID, if it exists
        String socketID = event.getSocketID();
        if (socketID != null) {
            Bukkit.getLogger().info("The socket ID associated with this event is: " + socketID);
        }
    }
}
```

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for the event to be properly handled.
{% endhint %}
