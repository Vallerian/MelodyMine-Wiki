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

# disableVoice()

## `disableVoice` Method in `MelodyManager` Class

{% hint style="info" %}
The `disableVoice` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to disable the voice functionality for a specific player on a specific server. It requires the player's name, UUID, the server they're on, and the target socket ID as parameters.
{% endhint %}

### Method Signature

```java
public void disableVoice(String playerName, String playerUuid, String playerServer, String targetSocketID)
```

### Parameters

<table><thead><tr><th width="201">Parameter</th><th width="113">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>playerName</code></td><td><code>String</code></td><td>The name of the player for whom the voice functionality is to be disabled.</td></tr><tr><td><code>playerUuid</code></td><td><code>String</code></td><td>The UUID of the player for whom the voice functionality is to be disabled.</td></tr><tr><td><code>playerServer</code></td><td><code>String</code></td><td>The server on which the player is currently playing.</td></tr><tr><td><code>targetSocketID</code></td><td><code>String</code></td><td>The ID of the socket that is to be targeted for the operation.</td></tr></tbody></table>

### Example Usage

Here is an example of how you might use the `disableVoice` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import org.bukkit.Bukkit;
import org.bukkit.entity.Player;

public class ExamplePlugin {

    public void disablePlayerVoice(Player player) {
        String playerName = player.getName();
        String playerUuid = player.getUniqueId().toString();
        String playerServer = Bukkit.getServer().getName();
        String targetSocketID = "exampleSocketID"; // Replace with actual socket ID

        MelodyManager.INSTANCE.disableVoice(playerName, playerUuid, playerServer, targetSocketID);

        Bukkit.getLogger().info("Voice functionality has been disabled for player: " + playerName + " to SocketID:" + targetSocketID);
    }
}
```

In this example, we're disabling the voice functionality for a specific player and then logging this action to the console.
