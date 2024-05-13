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

# PlayerLeaveWebEvent

{% hint style="info" %}
The `PlayerLeaveWebEvent` is a custom event in the MelodyMine plugin. This event is triggered when a player leaves the web interface of the plugin. The event contains a single property, `melodyPlayer`, which is an instance of the `MelodyPlayer` class representing the player who has left the web interface.
{% endhint %}

#### Properties

<table><thead><tr><th width="184">Property</th><th width="181">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who has left the web interface.</td></tr></tbody></table>

#### Example

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PlayerLeaveWebEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPlayerLeaveWeb(PlayerLeaveWebEvent event) {
        String playerName = event.getMelodyPlayer().getName();
        plugin.getLogger().info(playerName + " has left the web interface.");
    }
}
```

{% hint style="warning" %}
In this example, we create a class `ExampleListener` that implements the `Listener` interface. Inside this class, we define a method `onPlayerLeaveWeb` annotated with `@EventHandler`. This method will be called whenever a `PlayerLeaveWebEvent` is triggered. Inside this method, we retrieve the name of the player who left the web interface and log a message to the console.
{% endhint %}

