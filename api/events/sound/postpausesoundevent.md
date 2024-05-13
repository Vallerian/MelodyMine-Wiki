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

# PostPauseSoundEvent

## PostPauseSoundEvent

{% hint style="info" %}
The `PostPauseSoundEvent` is a custom event in Bukkit that is triggered after a sound is paused. This event provides information about the sound that was paused, whether the pause was sent to all players, and the socket ID associated with the event.
{% endhint %}

### Event Details

<table><thead><tr><th width="168">Field</th><th width="135">Type</th><th>Description</th></tr></thead><tbody><tr><td>soundName</td><td>String</td><td>The name of the sound that was paused.</td></tr><tr><td>sendToAll</td><td>Boolean</td><td>Indicates whether the pause was sent to all players.</td></tr><tr><td>socketID</td><td>String?</td><td>The socket ID associated with the event. This could be null.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostPauseSoundEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPostPauseSound(PostPauseSoundEvent event) {
        // Get the Bukkit logger
        Logger logger = Bukkit.getLogger();

        // Log the details of the paused sound
        logger.info("Sound paused: " + event.getSoundName());
        logger.info("Sent to all: " + event.isSendToAll());
        logger.info("Socket ID: " + event.getSocketID());
    }
}
```

In this example, we create a listener for the `PostPauseSoundEvent`. When the event is triggered, we log the details of the paused sound to the console using Bukkit's logger.

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable` method to ensure that it listens to the events.
{% endhint %}
