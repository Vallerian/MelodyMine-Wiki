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

# endCall()

## `endCall` Method in `MelodyManager` Class

{% hint style="info" %}
The `endCall` method is used to terminate an ongoing call between two players in the MelodyMine plugin. This method ends the call and updates the status of both players.
{% endhint %}

### Method Signature

```java
public void endCall(MelodyPlayer melodyPlayer, MelodyPlayer targetPlayer)
```

### Parameters

<table><thead><tr><th width="192">Parameter</th><th width="171">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who wants to end the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is the other participant of the call.</td></tr></tbody></table>

### Example

Here is an example of how to use the `endCall` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void terminateCall(String initiatorUUID, String targetUUID) {
        MelodyPlayer initiator = MelodyManager.INSTANCE.getMelodyPlayer(initiatorUUID);
        MelodyPlayer target = MelodyManager.INSTANCE.getMelodyPlayer(targetUUID);

        if (initiator != null && target != null) {
            MelodyManager.INSTANCE.endCall(initiator, target);
            Bukkit.getLogger().info("Call ended between " + initiator.getName() + " and " + target.getName());
        } else {
            Bukkit.getLogger().warning("One or both players not found.");
        }
    }
}
```

In this example, the `terminateCall` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instances for the initiator and target players using their UUIDs. It then uses the `endCall` method of the `MelodyManager` class to end a call between them. If the call is successfully terminated, a message is logged to the console. If one or both of the players are not found, a warning is logged instead.
