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

# PostDenyCallEvent

{% hint style="info" %}
The `PostDenyCallEvent` is a custom event in the Bukkit API that is called after a player denies a call request. This event provides information about the player who denied the call (`melodyPlayer`) and the player who was denied (`targetPlayer`).
{% endhint %}

### Event Details

<table><thead><tr><th width="204">Attribute</th><th width="187">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who denied the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who was denied the call.</td></tr><tr><td><code>canSendMessage</code></td><td><code>boolean</code></td><td>A flag indicating whether a message can be sent in response to the event.</td></tr></tbody></table>

### Example

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostDenyCallEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPostDenyCall(PostDenyCallEvent event) {
        // Get the player who denied the call
        MelodyPlayer melodyPlayer = event.getMelodyPlayer();

        // Get the player who was denied the call
        MelodyPlayer targetPlayer = event.getTargetPlayer();

        // Check if a message can be sent
        if (event.canSendMessage()) {
            // Log to console
            Bukkit.getLogger().info(melodyPlayer.getName() + " denied a call from " + targetPlayer.getName());
        }
    }
}
```

In this example, we create a listener for the `PostDenyCallEvent`. When the event is triggered, we retrieve the `MelodyPlayer` who denied the call and the `MelodyPlayer` who was denied the call. If the `canSendMessage` flag is true, we log a message to the console indicating that the call was denied.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable` method for it to work correctly.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(this), this);
}
```

