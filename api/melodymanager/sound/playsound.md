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

# playSound()

## `playSound` Method in `MelodyManager` Class

{% hint style="info" %}
The `playSound` method is used to play a sound in the MelodyMine plugin. This method can play a sound for a specific player or for all players, and the volume of the sound can be adjusted.
{% endhint %}

### Method Signature

```java
public void playSound(String soundName, boolean sendToAll, String socketID, Double volume)
```

### Parameters

<table><thead><tr><th width="184">Parameter</th><th width="131">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>soundName</code></td><td><code>String</code></td><td>The name of the sound to be played.</td></tr><tr><td><code>sendToAll</code></td><td><code>boolean</code></td><td>Determines whether the sound should be played for all players or not.</td></tr><tr><td><code>socketID</code></td><td><code>String</code></td><td>The socket ID of the player for whom the sound should be played. This is ignored if <code>sendToAll</code> is <code>true</code>.</td></tr><tr><td><code>volume</code></td><td><code>Double</code></td><td>The volume at which the sound should be played.</td></tr></tbody></table>

### Example

Here is an example of how to use the `playSound` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;

public class ExamplePlugin {

    public void playSoundForPlayer(String playerUUID, String soundName, double volume) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);

        if (player != null) {
            MelodyManager.INSTANCE.playSound(soundName, false, player.getSocketID(), volume);
            Bukkit.getLogger().info("Playing sound " + soundName + " for player " + player.getName());
        } else {
            Bukkit.getLogger().warning("Player not found.");
        }
    }
}
```

In this example, the `playSoundForPlayer` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `playSound` method of the `MelodyManager` class to play a sound for the player. If the sound is successfully played, a message is logged to the console. If the player is not found, a warning is logged instead.
