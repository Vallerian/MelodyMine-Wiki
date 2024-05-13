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

# PostPlaySoundEvent

## PostPlaySoundEvent

{% hint style="info" %}
The `PostPlaySoundEvent` is a custom event in the MelodyMine plugin. This event is triggered after a sound is played in the client for player. It provides information about the sound that was played, whether it was sent to all players, the socket ID of the player who triggered the sound, and the volume of the sound.
{% endhint %}

### Class Attributes

<table><thead><tr><th width="200">Attribute</th><th width="160">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td>String</td><td>The name of the sound that was played.</td></tr><tr><td><code>sendToAll</code></td><td>Boolean</td><td>Indicates whether the sound was sent to all players.</td></tr><tr><td><code>socketID</code></td><td>String</td><td>The socket ID of the player who triggered the sound.</td></tr><tr><td><code>volume</code></td><td>Double</td><td>The volume at which the sound was played.</td></tr></tbody></table>

### Listening to the Event

To listen to this event, you need to create a class that implements the `Listener` interface from the Bukkit API. Inside this class, you can then define a method annotated with `@EventHandler` to handle the `PostPlaySoundEvent`.

Here is an example:

```java
import ir.taher7.melodymine.api.events.PostPlaySoundEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class SoundEventListener implements Listener {

    @EventHandler
    public void onPostPlaySound(PostPlaySoundEvent event) {
        // Get the sound name
        String soundName = event.getSoundName();

        // Get the socket ID
        String socketID = event.getSocketID();

        // Log the information
        Bukkit.getLogger().info("Sound " + soundName + " was played by player with socket ID " + socketID);
    }
}
```

In this example, the `onPostPlaySound` method is called whenever a `PostPlaySoundEvent` is triggered. The method retrieves the name of the sound and the socket ID of the player who triggered the sound, and then logs this information to the console.

{% hint style="warning" %}
Remember to register your event listener with the Bukkit plugin manager to ensure that your `@EventHandler` methods are called when the events are triggered.
{% endhint %}
