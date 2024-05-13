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

# sendSoundSetting()

## `sendSoundSetting` Method in `MelodyManager` Class

{% hint style="info" %}
The `sendSoundSetting` method is used to send the sound settings of a player in the MelodyMine plugin. This method sends the sound settings to the client.
{% endhint %}

### Method Signature

```java
public void sendSoundSetting(String socketID)
```

### Parameters

<table><thead><tr><th width="145">Parameter</th><th width="142">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>socketID</code></td><td><code>String</code></td><td>The socket ID of the player whose sound settings are to be sent.</td></tr></tbody></table>

### Example

Here is an example of how to use the `sendSoundSetting` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void sendPlayerSoundSetting(String playerUUID) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.sendSoundSetting(player.getSocketID());
            Bukkit.getLogger().info("Sending sound settings for player " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `sendPlayerSoundSetting` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `sendSoundSetting` method of the `MelodyManager` class to send the player's sound settings. If the settings are successfully sent, a message is logged to the console. If the player is not found, a warning is logged instead.
