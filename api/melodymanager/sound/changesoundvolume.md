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

# changeSoundVolume()

## `changeSoundVolume` Method in `MelodyManager` Class

{% hint style="info" %}
The `changeSoundVolume` method is used to change the volume of a sound in the MelodyMine plugin. This method can change the volume of a sound for a specific player or for all players, depending on the parameters passed.
{% endhint %}

### Method Signature

```java
public void changeSoundVolume(String soundName, boolean sendToAll, String socketID, double volume)
```

### Parameters

<table><thead><tr><th width="166">Parameter</th><th width="128">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td><code>String</code></td><td>The name of the sound for which the volume is to be changed.</td></tr><tr><td><code>sendToAll</code></td><td><code>boolean</code></td><td>Determines whether the volume should be changed for all players or not.</td></tr><tr><td><code>socketID</code></td><td><code>String</code></td><td>The socket ID of the player for whom the volume should be changed. This is ignored if <code>sendToAll</code> is <code>true</code>.</td></tr><tr><td><code>volume</code></td><td><code>double</code></td><td>The new volume level for the sound.</td></tr></tbody></table>

### Example

Here is an example of how to use the `changeSoundVolume` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void changeVolumeForPlayer(String playerUUID, String soundName, double newVolume) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.changeSoundVolume(soundName, false, player.getSocketID(), newVolume);
            Bukkit.getLogger().info("Changed volume of sound " + soundName + " for player " + player.getName() + " to " + newVolume);
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `changeVolumeForPlayer` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `changeSoundVolume` method of the `MelodyManager` class to change the volume of a sound for the player. If the volume is successfully changed, a message is logged to the console. If the player is not found, a warning is logged instead.
