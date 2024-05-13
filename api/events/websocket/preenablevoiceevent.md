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

# PreEnableVoiceEvent

{% hint style="info" %}
The `PreEnableVoiceEvent` is a custom event in the Bukkit API. It is triggered before a player enables their voice in the MelodyMine plugin. This event provides information about the player and the target socket ID.
{% endhint %}

### Event Details

<table><thead><tr><th width="182">Field</th><th width="157">Type</th><th>Description</th></tr></thead><tbody><tr><td>playerName</td><td>String</td><td>The name of the player who is about to enable their voice.</td></tr><tr><td>playerUuid</td><td>String</td><td>The UUID of the player who is about to enable their voice.</td></tr><tr><td>playerServer</td><td>String</td><td>The server that the player is currently on.</td></tr><tr><td>targetSocketID</td><td>String</td><td>The socket ID of the target player.</td></tr></tbody></table>

### Methods

<table><thead><tr><th width="206">Method</th><th width="185">Return Type</th><th>Description</th></tr></thead><tbody><tr><td>getPlayer()</td><td>MelodyPlayer</td><td>Returns the <code>MelodyPlayer</code> instance of the player who is about to enable their voice.</td></tr><tr><td>getTargetPlayer()</td><td>MelodyPlayer</td><td>Returns the <code>MelodyPlayer</code> instance of the target player.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreEnableVoiceEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPreEnableVoice(PreEnableVoiceEvent event) {
        // Get the player's name
        String playerName = event.getPlayerName();

        // Get the target socket ID
        String targetSocketID = event.getTargetSocketID();

        // Log the information to the console
        Bukkit.getLogger().info(playerName + " is about to enable their voice. Target Socket ID: " + targetSocketID);
        
        getLogger().info("Player UUID: " + event.getPlayerUuid());
        getLogger().info("Player Server: " + event.getPlayerServer());
        getLogger().info("Target Socket ID: " + event.getTargetSocketID());
    }
}
```

In this example, we create a listener for the `PreEnableVoiceEvent`. When the event is triggered, we retrieve the player's name and the target socket ID, and then log this information to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method for it to work correctly.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new MyListener(), this);
}
```
