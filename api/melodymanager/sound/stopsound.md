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

# stopSound()

## `stopSound` Method in `MelodyManager` Class

{% hint style="info" %}
The `stopSound` method is used to stop a sound in the MelodyMine plugin. This method can stop a sound for a specific player or for all players, depending on the parameters passed.
{% endhint %}

### Method Signature

```java
public void stopSound(String soundName, boolean sendToAll, String socketID)
```

### Parameters

<table><thead><tr><th width="164">Parameter</th><th width="159">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td><code>String</code></td><td>The name of the sound to be stopped.</td></tr><tr><td><code>sendToAll</code></td><td><code>boolean</code></td><td>Determines whether the sound should be stopped for all players or not.</td></tr><tr><td><code>socketID</code></td><td><code>String</code></td><td>The socket ID of the player for whom the sound should be stopped. This is ignored if <code>sendToAll</code> is <code>true</code>.</td></tr></tbody></table>

### Example

Here is an example of how to use the `stopSound` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void stopSoundForPlayer(String playerUUID, String soundName) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.stopSound(soundName, false, player.getSocketID());
            Bukkit.getLogger().info("Stopping sound " + soundName + " for player " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `stopSoundForPlayer` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `stopSound` method of the `MelodyManager` class to stop a sound for the player. If the sound is successfully stopped, a message is logged to the console. If the player is not found, a warning is logged instead.
