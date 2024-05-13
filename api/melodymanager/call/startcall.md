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

# startCall()

## `startCall` Method in `MelodyManager` Class

{% hint style="info" %}
The `startCall` method is used to initiate a call between two players in the MelodyMine plugin. This method sets up the call and sends a request to the target player.
{% endhint %}

### Method Signature

```java
public void startCall(MelodyPlayer melodyPlayer, MelodyPlayer targetPlayer)
```

### Parameters

<table><thead><tr><th width="213">Parameter</th><th width="199">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who initiates the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is the target of the call.</td></tr></tbody></table>

### Example

Here is an example of how to use the `startCall` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void initiateCall(String initiatorUUID, String targetUUID) {
        MelodyPlayer initiator = MelodyManager.INSTANCE.getMelodyPlayer(initiatorUUID);
        MelodyPlayer target = MelodyManager.INSTANCE.getMelodyPlayer(targetUUID);

        if (initiator != null && target != null) {
            MelodyManager.INSTANCE.startCall(initiator, target);
            Bukkit.getLogger().info("Call initiated between " + initiator.getName() + " and " + target.getName());
        } else {
            Bukkit.getLogger().warning("One or both players not found.");
        }
    }
}
```

In this example, the `initiateCall` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instances for the initiator and target players using their UUIDs. It then uses the `startCall` method of the `MelodyManager` class to initiate a call between them. If the call is successfully initiated, a message is logged to the console. If one or both of the players are not found, a warning is logged instead.
