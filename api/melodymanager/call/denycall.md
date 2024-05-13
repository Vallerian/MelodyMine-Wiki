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

# denyCall()

## `denyCall` Method in `MelodyManager` Class

{% hint style="info" %}
The `denyCall` method is used to deny an incoming call between two players in the MelodyMine plugin. This method changes the status of both players to indicate that the call has been denied and cancels any pending tasks related to the call.
{% endhint %}

### Method Signature

```java
public void denyCall(MelodyPlayer melodyPlayer, MelodyPlayer targetPlayer)
```

### Parameters

<table><thead><tr><th width="201">Parameter</th><th width="212">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who is denying the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who initiated the call.</td></tr></tbody></table>

### Example

Here is an example of how to use the `denyCall` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void denyIncomingCall(String denierUUID, String initiatorUUID) {
        MelodyPlayer denier = MelodyManager.INSTANCE.getMelodyPlayer(denierUUID);
        MelodyPlayer initiator = MelodyManager.INSTANCE.getMelodyPlayer(initiatorUUID);

        if (denier != null && initiator != null) {
            MelodyManager.INSTANCE.denyCall(denier, initiator);
            Bukkit.getLogger().info("Call denied between " + denier.getName() + " and " + initiator.getName());
        } else {
            Bukkit.getLogger().warning("One or both players not found.");
        }
    }
}
```

In this example, the `denyIncomingCall` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instances for the denier and initiator players using their UUIDs. It then uses the `denyCall` method of the `MelodyManager` class to deny the call. If the call is successfully denied, a message is logged to the console. If one or both of the players are not found, a warning is logged instead.
