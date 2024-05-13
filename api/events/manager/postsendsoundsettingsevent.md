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

# PostSendSoundSettingsEvent

{% hint style="info" %}
The `PostSendSoundSettingsEvent` is a custom event in Bukkit that is triggered after the sound settings are sent to the client. This event is useful for developers who want to perform certain actions or checks after the sound settings have been sent.
{% endhint %}

#### Class Properties

<table><thead><tr><th width="173">Property</th><th width="144">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>socketID</code></td><td><code>String</code></td><td>The ID of the socket to which the sound settings were sent.</td></tr></tbody></table>

#### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PostSendSoundSettingsEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPostSendSoundSettings(PostSendSoundSettingsEvent event) {
        // Get the socket ID
        String socketID = event.getSocketID();

        // Print the socket ID to the console
        Bukkit.getLogger().info("Sound settings were sent to the socket with ID: " + socketID);
    }
}
```

In this example, we create a listener for the `PostSendSoundSettingsEvent`. When the event is triggered, we retrieve the `socketID` from the event and print it to the console.

{% hint style="warning" %}
Remember to register your listener in your plugin's `onEnable()` method to ensure that it listens to the event.
{% endhint %}

```java
@Override
public void onEnable() {
    getServer().getPluginManager().registerEvents(new ExampleListener(), this);
}
```

This will ensure that the `ExampleListener` class is listening for the `PostSendSoundSettingsEvent` and will execute the `onPostSendSoundSettings` method when the event is triggered.
