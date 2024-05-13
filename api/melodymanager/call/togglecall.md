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

# toggleCall()

## `toggleCall` Method in `MelodyManager` Class

{% hint style="info" %}
The `toggleCall` method is used to toggle the call status of a player in the MelodyMine plugin. This method changes the `callToggle` status of the player, which determines whether the player can receive calls or not.
{% endhint %}

### Method Signature

```java
public void toggleCall(MelodyPlayer melodyPlayer)
```

### Parameters

<table><thead><tr><th width="190">Parameter</th><th width="181">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player whose call status is to be toggled.</td></tr></tbody></table>

### Example

Here is an example of how to use the `toggleCall` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void togglePlayerCallStatus(String playerUUID) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.toggleCall(player);
            Bukkit.getLogger().info("Call status toggled for player " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `togglePlayerCallStatus` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `toggleCall` method of the `MelodyManager` class to toggle the call status of the player. If the call status is successfully toggled, a message is logged to the console. If the player is not found, a warning is logged instead.
