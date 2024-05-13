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

# pauseSound()

## `pauseSound` Method in `MelodyManager` Class

{% hint style="info" %}
The `pauseSound` method is used to pause a sound in the MelodyMine plugin. This method can pause a sound for a specific player or for all players, depending on the parameters passed.
{% endhint %}

### Method Signature

```java
public void pauseSound(String soundName, boolean sendToAll, String socketID)
```

### Parameters

<table><thead><tr><th width="166">Parameter</th><th width="134">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td><code>String</code></td><td>The name of the sound to be paused.</td></tr><tr><td><code>sendToAll</code></td><td><code>boolean</code></td><td>Determines whether the sound should be paused for all players or not.</td></tr><tr><td><code>socketID</code></td><td><code>String</code></td><td>The socket ID of the player for whom the sound should be paused. This is ignored if <code>sendToAll</code> is <code>true</code>.</td></tr></tbody></table>

### Example

Here is an example of how to use the `pauseSound` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void pauseSoundForPlayer(String playerUUID, String soundName) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.pauseSound(soundName, false, player.getSocketID());
            Bukkit.getLogger().info("Pausing sound " + soundName + " for player " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `pauseSoundForPlayer` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `pauseSound` method of the `MelodyManager` class to pause a sound for the player. If the sound is successfully paused, a message is logged to the console. If the player is not found, a warning is logged instead.
