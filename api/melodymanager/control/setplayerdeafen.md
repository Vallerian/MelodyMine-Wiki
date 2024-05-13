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

# setPlayerDeafen()

## `setPlayerDeafen` Method in `MelodyManager` Class

{% hint style="info" %}
The `setPlayerDeafen` method is a part of the `MelodyManager` class. This method is used to set the deafen status of a player in the MelodyMine plugin. The deafen status determines whether the player can hear other players in the voice chat or not.
{% endhint %}

### Method Signature

```java
public void setPlayerDeafen(MelodyPlayer melodyPlayer, boolean value)
```

### Parameters

<table><thead><tr><th width="180">Parameter</th><th width="173">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The player whose deafen status is to be set.</td></tr><tr><td><code>value</code></td><td><code>boolean</code></td><td>The deafen status to be set. If <code>true</code>, the player will not be able to hear others in the voice chat. If <code>false</code>, the player will be able to hear others.</td></tr></tbody></table>

### Usage

To use this method in another plugin, you need to get an instance of the `MelodyManager` class and call the `setPlayerDeafen` method on it. Here is an example:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;
import org.bukkit.Bukkit;
import org.bukkit.entity.Player;

public class ExamplePlugin {
    public void deafenPlayer(Player player, boolean value) {
        MelodyPlayer melodyPlayer = MelodyManager.INSTANCE.getOnlinePlayer(player.getUniqueId().toString());
        if (melodyPlayer != null) {
            MelodyManager.INSTANCE.setPlayerDeafen(melodyPlayer, value);
            Bukkit.getLogger().info("Set deafen status of player " + player.getName() + " to " + value);
        }
    }
}
```

In this example, the `deafenPlayer` method takes a `Player` object and a boolean value. It retrieves the `MelodyPlayer` object corresponding to the `Player` and sets the deafen status of the `MelodyPlayer` to the provided boolean value. It then logs the action to the console.
