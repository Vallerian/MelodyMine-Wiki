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

# PreSendQRCodeEvent

{% hint style="info" %}
The `PreSendQRCodeEvent` is a custom event in the Bukkit API. It is triggered before a QR code is sent to a player. This event is cancellable, meaning you can prevent the QR code from being sent to the player by cancelling this event in your event handler.
{% endhint %}

### Class Structure

<table><thead><tr><th width="271">Method</th><th width="146">Return Type</th><th>Description</th></tr></thead><tbody><tr><td><code>getPlayer()</code></td><td><code>Player</code></td><td>Returns the player to whom the QR code is about to be sent.</td></tr><tr><td><code>isCancelled()</code></td><td><code>boolean</code></td><td>Checks if the event is cancelled.</td></tr><tr><td><code>setCancelled(boolean)</code></td><td><code>void</code></td><td>Sets the cancellation state of this event. A cancelled event will not be executed in the server, but will still pass to other plugins.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;
import ir.taher7.melodymine.api.events.PreSendQRCodeEvent;

public class QRCodeListener implements Listener {

    @EventHandler
    public void onPreSendQRCode(PreSendQRCodeEvent event) {
        // Get the player to whom the QR code is about to be sent
        Player player = event.getPlayer();

        // Print a message to the console
        Bukkit.getLogger().info("About to send a QR code to " + player.getName());

        // You can cancel the event to prevent the QR code from being sent
        // For example, let's not send the QR code to players named "TAHER7"
        if (player.getName().equalsIgnoreCase("TAHER7")) {
            event.setCancelled(true);
            Bukkit.getLogger().info("Cancelled sending QR code to " + player.getName());
        }
    }
}
```

In this example, we're listening for the `PreSendQRCodeEvent`. When the event is triggered, we're logging a message to the console. If the player's name is "TAHER7", we're cancelling the event, which prevents the QR code from being sent, and logging another message to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method, otherwise Bukkit won't know to pass events to it.
{% endhint %}
