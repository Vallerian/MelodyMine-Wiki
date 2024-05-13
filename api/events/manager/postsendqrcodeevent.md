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

# PostSendQRCodeEvent

{% hint style="info" %}
The `PostSendQRCodeEvent` is a custom event in the Bukkit API. It is triggered after a QR code is sent to a player. This event provides a way to execute custom logic in response to the QR code being sent.
{% endhint %}

#### Class Structure

<table><thead><tr><th width="180">Method/Variable</th><th width="154">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>player</code></td><td><code>Player</code></td><td>The player to whom the QR code was sent.</td></tr></tbody></table>

#### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostSendQRCodeEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class QRCodeListener implements Listener {

    @EventHandler
    public void onQRCodeSent(PostSendQRCodeEvent event) {
        // Get the player to whom the QR code was sent
        Player player = event.getPlayer();

        // Print a message to the console
        Bukkit.getLogger().info("A QR code was sent to " + player.getName());
    }
}
```

In this example, we create a listener for the `PostSendQRCodeEvent`. When the event is triggered, we retrieve the player to whom the QR code was sent and print a message to the console.

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable()` method to ensure that it listens to the event.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new QRCodeListener(), this);
}
```

This will ensure that your `QRCodeListener` is listening for the `PostSendQRCodeEvent` when your plugin is enabled.
