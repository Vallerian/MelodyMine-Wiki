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

# PostEnableVoiceEvent

## PostEnableVoiceEvent

{% hint style="info" %}
The `PostEnableVoiceEvent` is a custom event in the MelodyMine plugin. This event is triggered after a player enables their voice chat. It provides information about the player who enabled their voice chat.
{% endhint %}

### Event Details

<table><thead><tr><th width="216">Field</th><th width="129">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>playerName</code></td><td><code>String</code></td><td>The name of the player who enabled their voice chat.</td></tr><tr><td><code>playerUuid</code></td><td><code>String</code></td><td>The UUID of the player who enabled their voice chat.</td></tr><tr><td><code>playerServer</code></td><td><code>String</code></td><td>The server of the player who enabled their voice chat.</td></tr><tr><td><code>targetSocketID</code></td><td><code>String</code></td><td>The socket ID of the player who enabled their voice chat.</td></tr></tbody></table>

### Methods

<table><thead><tr><th width="228">Method</th><th width="184">Return Type</th><th>Description</th></tr></thead><tbody><tr><td>getPlayer()</td><td><code>MelodyPlayer</code></td><td>Returns the <code>MelodyPlayer</code> instance of the player who enabled their voice chat.</td></tr><tr><td><code>getTargetPlayer()</code></td><td><code>MelodyPlayer</code></td><td>Returns the <code>MelodyPlayer</code> instance of the player who is the target of the voice chat.</td></tr></tbody></table>

### Example Usage

Here is an example of how to listen to this event using the Bukkit event API in Java:

```java
import ir.taher7.melodymine.api.events.PostEnableVoiceEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class MyListener implements Listener {

    @EventHandler
    public void onPostEnableVoice(PostEnableVoiceEvent event) {
        // Get the player's name who enabled their voice chat
        String playerName = event.getPlayerName();

        // Log the player's name to the console
        Bukkit.getLogger().info(playerName + " has enabled their voice chat.");
    }
}
```

In this example, we create a listener for the `PostEnableVoiceEvent`. When the event is triggered, we retrieve the name of the player who enabled their voice chat and log it to the console.
