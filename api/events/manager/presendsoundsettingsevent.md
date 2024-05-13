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

# PreSendSoundSettingsEvent

{% hint style="info" %}
The `PreSendSoundSettingsEvent` is a custom event in the Bukkit API. It is triggered before the sound settings are sent to the client. This event is cancellable, meaning you can prevent the sound settings from being sent to the client.
{% endhint %}

#### Class Structure

<table><thead><tr><th width="190">Method/Variable</th><th width="164">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>socketID</code></td><td><code>String</code></td><td>The ID of the socket to which the sound settings are being sent.</td></tr><tr><td><code>isCancelled</code></td><td><code>Boolean</code></td><td>A flag indicating whether the event is cancelled. If true, the sound settings will not be sent.</td></tr></tbody></table>

#### Example Usage

Here is an example of how to listen to this event:

```java
import ir.taher7.melodymine.api.events.PreSendSoundSettingsEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPreSendSoundSettings(PreSendSoundSettingsEvent event) {
        // Get the socket ID
        String socketID = event.getSocketID();

        // Log the socket ID to the console
        Bukkit.getLogger().info("Preparing to send sound settings to socket: " + socketID);

        // You can cancel the event like this
        // event.setCancelled(true);
    }
}
```

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable` method to ensure that it's active.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(), this);
}
```

This listener will log the ID of the socket to which the sound settings are being sent every time the `PreSendSoundSettingsEvent` is triggered. You can also cancel the event to prevent the sound settings from being sent.
