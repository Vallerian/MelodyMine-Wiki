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

# PostEnableAdminMode

{% hint style="info" %}
The `PostEnableAdminMode` class is an event class in Bukkit. It is triggered after a player's admin mode is enabled in the MelodyMine plugin. This class extends the `Event` class provided by the Bukkit API.
{% endhint %}

The class has one field:

<table><thead><tr><th width="209">Field</th><th width="207">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player for whom the admin mode has been enabled.</td></tr></tbody></table>

### Listening to the Event

You can listen to this event by creating a class that implements the `Listener` interface provided by the Bukkit API. Inside this class, you can define a method annotated with `@EventHandler` to handle the `PostEnableAdminMode` event.

Here is an example:

```java
import ir.taher7.melodymine.api.events.PostEnableAdminMode;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class AdminModeListener implements Listener {

    @EventHandler
    public void onAdminModeEnabled(PostEnableAdminMode event) {
        // Get the player who has enabled admin mode
        MelodyPlayer player = event.getMelodyPlayer();

        // Log the player's name to the console
        Bukkit.getLogger().info(player.getName() + " has enabled admin mode.");
    }
}
```

In this example, we create a class `AdminModeListener` that implements the `Listener` interface. Inside this class, we define a method `onAdminModeEnabled` that is annotated with `@EventHandler`. This method is automatically called when the `PostEnableAdminMode` event is triggered. Inside this method, we retrieve the player who has enabled admin mode and log their name to the console.

{% hint style="warning" %}
Remember to register your listener class with the Bukkit plugin manager to ensure that your `@EventHandler` methods are called when the events are triggered.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new AdminModeListener(), this);
}
```
