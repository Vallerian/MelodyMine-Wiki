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

# PostRenewDataEvent

{% hint style="info" %}
### PostRenewDataEvent

The `PostRenewDataEvent` is a custom event in the MelodyMine plugin. This event is triggered after the renewal of data in the client. The data being renewed is encapsulated in the `RenewData` object, which is passed to the event.
{% endhint %}

<table><thead><tr><th width="199">Method</th><th>Description</th></tr></thead><tbody><tr><td><code>getData()</code></td><td>Returns the <code>RenewData</code> object associated with this event.</td></tr></tbody></table>

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PostRenewDataEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ExampleListener implements Listener {

    @EventHandler
    public void onPostRenewData(PostRenewDataEvent event) {
        // Access the RenewData object from the event
        RenewData data = event.getData();

        // Use the data in some way, for example, print some information to the console
        Bukkit.getLogger().info("PostRenewDataEvent triggered with " + data.getP().size() + " players.");
    }
}
```

In this example, the `ExampleListener` class implements the `Listener` interface from the Bukkit API. The `onPostRenewData` method is decorated with the `@EventHandler` annotation, indicating that it should be called when the `PostRenewDataEvent` is triggered. Inside this method, we retrieve the `RenewData` object from the event and print the number of players in the data to the console.

{% hint style="warning" %}
Remember to register your listener with the Bukkit plugin manager to ensure your event handler method is called.
{% endhint %}
