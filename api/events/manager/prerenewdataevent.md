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

# PreRenewDataEvent

{% hint style="info" %}
The `PreRenewDataEvent` is a custom event in the MelodyMine plugin. It is triggered before the renewal of data in the client. This event is cancellable, which means you can prevent the data renewal process from happening if certain conditions are met in your plugin.
{% endhint %}

### Class Structure

<table><thead><tr><th width="316">Method/Variable</th><th width="169">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>data</code></td><td><code>RenewData</code></td><td>An instance of the <code>RenewData</code> class which contains the data to be renewed.</td></tr><tr><td><code>isCancelled()</code></td><td><code>boolean</code></td><td>Checks if the event is cancelled.</td></tr><tr><td><code>setCancelled(boolean)</code></td><td><code>void</code></td><td>Sets the cancellation state of the event.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API:

```java
import ir.taher7.melodymine.api.events.PreRenewDataEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPreRenewData(PreRenewDataEvent event) {
        // Access the RenewData instance
        RenewData data = event.getData();

        // Print the data to console
        Bukkit.getLogger().info("PreRenewDataEvent triggered with data: " + data.toString());

        // Cancel the event based on a condition
        if (data.getP().size() > 10) {
            event.setCancelled(true);
            Bukkit.getLogger().info("PreRenewDataEvent cancelled due to data size being greater than 10.");
        }
    }
}
```

In this example, we're listening for the `PreRenewDataEvent`. When the event is triggered, we're logging the `RenewData` instance to the console. If the size of the `p` list in the `RenewData` instance is greater than 10, we cancel the event and log a message to the console.

{% hint style="warning" %}
Remember to register your event listener in your plugin's `onEnable()` method for the event to be properly handled.
{% endhint %}
