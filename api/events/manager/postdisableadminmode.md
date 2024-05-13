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

# PostDisableAdminMode

{% hint style="info" %}
The `PostDisableAdminMode` event is triggered after the admin mode of a `MelodyPlayer` is disabled. This event provides an opportunity to perform additional actions or checks after the admin mode has been disabled.
{% endhint %}

### Class Properties

<table><thead><tr><th width="202">Property</th><th width="199">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player whose admin mode has been disabled.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PostDisableAdminMode;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPostDisableAdminMode(PostDisableAdminMode event) {
        // Get the player whose admin mode has been disabled
        MelodyPlayer player = event.getMelodyPlayer();

        // Print a message to the console
        Bukkit.getLogger().info(player.getName() + "'s admin mode has been disabled.");
    }
}
```

In this example, we create a listener for the `PostDisableAdminMode` event. When the event is triggered, we retrieve the `MelodyPlayer` whose admin mode has been disabled and print a message to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for it to work.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyListener(), this);
}
```
