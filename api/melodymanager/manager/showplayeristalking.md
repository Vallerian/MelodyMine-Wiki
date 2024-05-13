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

# showPlayerIsTalking()

## `showPlayerIsTalking` Method in `MelodyManager` Class

{% hint style="info" %}
The `showPlayerIsTalking` method is used to display the talking status of a player in the MelodyMine plugin. This method updates the player's status on the BossBar and NameTag based on whether the player is muted, self-muted, or actively talking.
{% endhint %}

### Method Signature

```java
public void showPlayerIsTalking(MelodyPlayer player)
```

### Parameters

<table><thead><tr><th width="137">Parameter</th><th width="171">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>player</code></td><td><code>MelodyPlayer</code></td><td>The player whose talking status is to be displayed.</td></tr></tbody></table>

### Example

Here is an example of how to use the `showPlayerIsTalking` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void displayTalkingStatus(String playerUUID) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.showPlayerIsTalking(player);
            Bukkit.getLogger().info("Displaying talking status for player " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `displayTalkingStatus` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `showPlayerIsTalking` method of the `MelodyManager` class to display the talking status of the player. If the status is successfully displayed, a message is logged to the console. If the player is not found, a warning is logged instead.
