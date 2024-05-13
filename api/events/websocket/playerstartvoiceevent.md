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

# PlayerStartVoiceEvent

{% hint style="info" %}
The `PlayerStartVoiceEvent` is a custom event in the MelodyMine plugin. This event is triggered when a player starts using the voice chat feature in the client. The event contains a single property, `melodyPlayer`, which is an instance of the `MelodyPlayer` class representing the player who started the voice chat.
{% endhint %}

### Properties

<table><thead><tr><th width="193">Property</th><th width="173">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who started the voice chat.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PlayerStartVoiceEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin implements Listener {

    @Override
    public void onEnable() {
        getServer().getPluginManager().registerEvents(this, this);
    }

    @EventHandler
    public void onPlayerStartVoice(PlayerStartVoiceEvent event) {
        getLogger().info(event.getMelodyPlayer().getName() + " has started voice chat.");
    }
}
```

{% hint style="warning" %}
In this example, we create a listener for the `PlayerStartVoiceEvent`. When the event is triggered, the `onPlayerStartVoice` method is called. Inside this method, we log a message to the console indicating the name of the player who started the voice chat.
{% endhint %}
