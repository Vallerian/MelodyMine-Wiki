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

# PostUnMutePlayerEvent

{% hint style="info" %}
The `PostUnMutePlayerEvent` is a custom event in the MelodyMine plugin. This event is triggered after a player has been server unmuted. It provides access to the `MelodyPlayer` instance of the player who was unmuted.
{% endhint %}

### Class Structure

<table><thead><tr><th width="190">Method/Variable</th><th width="196">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who has been unmuted.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PostUnMutePlayerEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import org.bukkit.plugin.java.JavaPlugin;

public class ExampleListener implements Listener {

    private JavaPlugin plugin;

    public ExampleListener(JavaPlugin plugin) {
        this.plugin = plugin;
    }

    @EventHandler
    public void onPostUnMutePlayer(PostUnMutePlayerEvent event) {
        // Get the MelodyPlayer who was unmuted
        MelodyPlayer player = event.getMelodyPlayer();

        // Log to console
        plugin.getLogger().info(player.getName() + " has been unmuted.");
    }
}
```

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable` method like so:

```java
getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
```
{% endhint %}
