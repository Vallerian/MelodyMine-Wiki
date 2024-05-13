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

# PlayerJoinWebEvent

{% hint style="info" %}
The `PlayerJoinWebEvent` is a custom event in the MelodyMine plugin. This event is triggered when a player joins the web client of the MelodyMine voice chat system. The event contains a single property, `melodyPlayer`, which is an instance of the `MelodyPlayer` class representing the player who has joined the web client.
{% endhint %}

### Properties

<table><thead><tr><th width="193">Property</th><th width="191">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who has joined the web client.</td></tr></tbody></table>

### Example

Here is an example of how to listen to the `PlayerJoinWebEvent` using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PlayerJoinWebEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private final JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPlayerJoinWeb(PlayerJoinWebEvent event) {
        String playerName = event.getMelodyPlayer().getName();
        plugin.getLogger().info(playerName + " has joined the web client.");
    }
}
```

{% hint style="warning" %}
In this example, we create a class `ExampleListener` that implements the `Listener` interface. Inside this class, we define a method `onPlayerJoinWeb` with the `@EventHandler` annotation to specify that this method should be called when the `PlayerJoinWebEvent` is triggered. In the method body, we retrieve the name of the player who has joined the web client and log a message to the console.
{% endhint %}

Remember to register the event listener in your plugin's `onEnable` method:

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
}
```

This will ensure that your `onPlayerJoinWeb` method is called whenever a `PlayerJoinWebEvent` is triggered.
