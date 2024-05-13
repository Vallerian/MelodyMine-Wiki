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

# checkPlayerWebConnection()

## `checkPlayerWebConnection` Method in `MelodyManager` Class

{% hint style="info" %}
The `checkPlayerWebConnection` method is used to verify the web connection of a player in the MelodyMine plugin. This method checks if the player is online on the web.
{% endhint %}

### Method Signature

```java
public void checkPlayerWebConnection(MelodyPlayer player)
```

### Parameters

<table><thead><tr><th width="143">Parameter</th><th width="190">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>player</code></td><td><code>MelodyPlayer</code></td><td>The player whose web connection is to be checked.</td></tr></tbody></table>

### Example

Here is an example of how to use the `checkPlayerWebConnection` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void checkWebConnection(String playerUUID) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.checkPlayerWebConnection(player);
            Bukkit.getLogger().info("Checking web connection for player " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `checkWebConnection` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `checkPlayerWebConnection` method of the `MelodyManager` class to check the player's web connection. If the check is successfully initiated, a message is logged to the console. If the player is not found, a warning is logged instead.
