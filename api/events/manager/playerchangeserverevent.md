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

# PlayerChangeServerEvent

{% hint style="info" %}
The `PlayerChangeServerEvent` is a custom event class in the MelodyMine plugin. This event is triggered when a player changes their server in the context of the plugin. The event carries information about the player who triggered the event in the form of a `MelodyPlayer` object.
{% endhint %}

### Event Information

<table><thead><tr><th width="180">Attribute</th><th width="193">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who has changed their server. This object contains all the information about the player in the context of the MelodyMine plugin.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PlayerChangeServerEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPlayerChangeServer(PlayerChangeServerEvent event) {
        // Get the MelodyPlayer who changed their server
        MelodyPlayer melodyPlayer = event.getMelodyPlayer();

        // Get the player's name
        String playerName = melodyPlayer.getName();

        // Log the server change to the console
        Bukkit.getLogger().info(playerName + " has changed their server.");
    }
}
```

{% hint style="warning" %}
Remember to register your listener class in your plugin's `onEnable` method to ensure that the event handler is called when the event is triggered.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(), this);
}
```

This example listens for the `PlayerChangeServerEvent` and when the event is triggered, it retrieves the `MelodyPlayer` who changed their server and logs a message to the console.
