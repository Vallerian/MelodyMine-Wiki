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

# sendStartQRCode()

## `sendStartQRCode` Method in `MelodyManager` Class

{% hint style="info" %}
The `sendStartQRCode` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to send a QR code to a player in the game. The QR code is placed in a specific slot in the player's inventory or in the player's offhand.
{% endhint %}

### Method Signature

```java
public void sendStartQRCode(Player player, int slot, boolean offhand)
```

### Parameters

<table><thead><tr><th width="141">Parameter</th><th width="127">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>player</code></td><td><code>Player</code></td><td>The player to whom the QR code will be sent.</td></tr><tr><td><code>slot</code></td><td><code>int</code></td><td>The inventory slot where the QR code will be placed.</td></tr><tr><td><code>offhand</code></td><td><code>boolean</code></td><td>If <code>true</code>, the QR code will be placed in the player's offhand. If <code>false</code>, it will be placed in the specified inventory slot.</td></tr></tbody></table>

### Example Usage

Here is an example of how to use the `sendStartQRCode` method in another plugin:

```java
import org.bukkit.entity.Player;
import org.bukkit.Bukkit;
import ir.taher7.melodymine.core.MelodyManager;

public class ExamplePlugin {

    public void sendQRCodeToPlayer(String playerName) {
        Player player = Bukkit.getPlayer(playerName);
        if (player != null) {
            MelodyManager.INSTANCE.sendStartQRCode(player, 0, false);
            Bukkit.getLogger().info("Sent QR code to " + playerName);
        } else {
            Bukkit.getLogger().warning("Player " + playerName + " not found.");
        }
    }
}
```

In this example, the `sendQRCodeToPlayer` method in the `ExamplePlugin` class retrieves a player by their name, sends a QR code to the first slot of their inventory using the `sendStartQRCode` method, and logs a message to the console. If the player is not found, a warning is logged to the console.
