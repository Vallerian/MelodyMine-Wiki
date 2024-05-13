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

# PostStopSoundEvent

{% hint style="info" %}
The `PostStopSoundEvent` is a custom event in the Bukkit API that is triggered after a sound has been stopped. This event provides information about the sound that was stopped, whether it was sent to all players, and the socket ID associated with the event.
{% endhint %}

### Class Structure

<table><thead><tr><th width="151">Field</th><th width="112">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td><code>String</code></td><td>The name of the sound that was stopped.</td></tr><tr><td><code>sendToAll</code></td><td><code>Boolean</code></td><td>Indicates whether the sound was sent to all players.</td></tr><tr><td><code>socketID</code></td><td><code>String?</code></td><td>The socket ID associated with the event. This could be null.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostStopSoundEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPostStopSound(PostStopSoundEvent event) {
        String soundName = event.getSoundName();
        boolean sendToAll = event.isSendToAll();
        String socketID = event.getSocketID();

        System.out.println("Sound " + soundName + " has been stopped.");
        System.out.println("Was the sound sent to all players? " + (sendToAll ? "Yes" : "No"));
        System.out.println("The associated socket ID is: " + socketID);
    }
}
```

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable()` method to ensure that it listens to the `PostStopSoundEvent`.
{% endhint %}

In the above example, we're implementing the `Listener` interface and defining an `onPostStopSound` method annotated with `@EventHandler`. This method will be called whenever a `PostStopSoundEvent` is triggered. Inside this method, we're retrieving the sound name, whether the sound was sent to all players, and the socket ID from the event, and then printing these details to the console.
