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

# acceptCall()

## `acceptCall` Method in `MelodyManager` Class

{% hint style="info" %}
The `acceptCall` method is used to accept an incoming call between two players in the MelodyMine plugin. This method changes the status of both players to indicate that they are in a call and cancels any pending tasks related to the call.
{% endhint %}

### Method Signature

```java
public void acceptCall(MelodyPlayer melodyPlayer, MelodyPlayer targetPlayer)
```

### Parameters

<table><thead><tr><th width="201">Parameter</th><th width="182">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is accepting the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who initiated the call.</td></tr></tbody></table>

### Example

Here is an example of how to use the `acceptCall` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void acceptIncomingCall(String acceptorUUID, String initiatorUUID) {
        MelodyPlayer acceptor = MelodyManager.INSTANCE.getMelodyPlayer(acceptorUUID);
        MelodyPlayer initiator = MelodyManager.INSTANCE.getMelodyPlayer(initiatorUUID);

        if (acceptor != null && initiator != null) {
            MelodyManager.INSTANCE.acceptCall(acceptor, initiator);
            Bukkit.getLogger().info("Call accepted between " + acceptor.getName() + " and " + initiator.getName());
        } else {
            Bukkit.getLogger().warning("One or both players not found.");
        }
    }
}
```

In this example, the `acceptIncomingCall` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instances for the acceptor and initiator players using their UUIDs. It then uses the `acceptCall` method of the `MelodyManager` class to accept the call. If the call is successfully accepted, a message is logged to the console. If one or both of the players are not found, a warning is logged instead.
