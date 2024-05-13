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

# PlayerEndVoiceEvent

{% hint style="info" %}
The `PlayerEndVoiceEvent` is a custom event in the MelodyMine plugin. This event is triggered when a player ends their voice session on the client. The event contains a single property, `melodyPlayer`, which is an instance of the `MelodyPlayer` class representing the player who ended their voice session.
{% endhint %}

### Properties

<table><thead><tr><th width="193">Property</th><th width="182">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who ended their voice session.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PlayerEndVoiceEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class MyPlugin extends JavaPlugin implements Listener {

    @Override
    public void onEnable() {
        getServer().getPluginManager().registerEvents(this, this);
    }

    @EventHandler
    public void onPlayerEndVoice(PlayerEndVoiceEvent event) {
        String playerName = event.getMelodyPlayer().getName();
        getLogger().info(playerName + " has ended their voice session.");
    }
}
```

{% hint style="warning" %}
In this example, we're creating a listener for the `PlayerEndVoiceEvent`. When a player ends their voice session, the `onPlayerEndVoice` method is called, and the player's name is logged to the console with a message indicating that they have ended their voice session.
{% endhint %}
