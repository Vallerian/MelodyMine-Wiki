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

# setPlayerSelfMute()

## `setPlayerSelfMute` Method in `MelodyManager` Class

{% hint style="info" %}
The `setPlayerSelfMute` method is a part of the `MelodyManager` class. This method is used to mute or unmute a player in the MelodyMine plugin.
{% endhint %}

### Method Signature

```java
public void setPlayerSelfMute(MelodyPlayer melodyPlayer, boolean value)
```

### Parameters

<table><thead><tr><th width="195">Parameter</th><th width="191">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player who will be muted or unmuted.</td></tr><tr><td><code>value</code></td><td><code>boolean</code></td><td>The mute status to be set. <code>true</code> for mute and <code>false</code> for unmute.</td></tr></tbody></table>

### Usage

{% hint style="warning" %}
To use this method, you need to have an instance of the `MelodyPlayer` class which represents the player you want to mute or unmute. You also need to decide the mute status.
{% endhint %}

Here is an example of how to use this method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;
import org.bukkit.Bukkit;
import org.bukkit.entity.Player;

public class ExamplePlugin {
    public void mutePlayerExample(String playerName, boolean muteStatus) {
        Player player = Bukkit.getPlayer(playerName);
        if (player != null) {
            MelodyPlayer melodyPlayer = MelodyManager.INSTANCE.getMelodyPlayer(player.getUniqueId());
            if (melodyPlayer != null) {
                MelodyManager.INSTANCE.setPlayerSelfMute(melodyPlayer, muteStatus);
                Bukkit.getLogger().info("Set mute status of " + playerName + " to " + muteStatus);
            }
        }
    }
}
```

In this example, we first get the `Player` object from Bukkit using the player's name. Then, we get the `MelodyPlayer` instance for that player. Finally, we call the `setPlayerSelfMute` method on the `MelodyManager` instance to set the mute status of the player. We also log the action to the console.
