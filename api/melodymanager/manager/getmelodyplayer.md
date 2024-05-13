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

# getMelodyPlayer()

## `getMelodyPlayer` Method in `MelodyManager` Class

{% hint style="info" %}
The `getMelodyPlayer` method is used to retrieve the `MelodyPlayer` instance for a player in the MelodyMine plugin. This method uses the player's UUID to find the corresponding `MelodyPlayer` instance.
{% endhint %}

### Method Signature

```java
public MelodyPlayer getMelodyPlayer(String uuid)
```

### Parameters

<table><thead><tr><th width="144">Parameter</th><th width="144">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>uuid</code></td><td><code>String</code></td><td>The UUID of the player whose <code>MelodyPlayer</code> instance is to be retrieved.</td></tr></tbody></table>

### Example

Here is an example of how to use the `getMelodyPlayer` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void printPlayerName(String playerUUID) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            Bukkit.getLogger().info("Player name: " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `printPlayerName` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then prints the player's name to the console. If the player is not found, a warning is logged instead.
