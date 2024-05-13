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

# sendStartLink()

## `sendStartLink` Method in `MelodyManager` Class

{% hint style="info" %}
The `sendStartLink` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to send a start link to a player.
{% endhint %}

### Method Signature

```java
public void sendStartLink(Player player)
```

### Parameters

<table><thead><tr><th width="157">Parameter</th><th width="136">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>player</code></td><td><code>Player</code></td><td>The player to whom the start link is to be sent.</td></tr></tbody></table>

### Usage

To use this method in another plugin, you need to import the `MelodyManager` class and call the `sendStartLink` method on its instance. Here is an example:

```java
import ir.taher7.melodymine.core.MelodyManager;
import org.bukkit.entity.Player;
import org.bukkit.plugin.java.JavaPlugin;

public class ExamplePlugin extends JavaPlugin {

    @Override
    public void onEnable() {
        Player player = getServer().getPlayer("playerName");
        if (player != null) {
            MelodyManager.INSTANCE.sendStartLink(player);
            getLogger().info("Start link sent to the player.");
        }
    }
}
```

{% hint style="warning" %}
Make sure the player is online before calling this method, as it requires an active `Player` object. If the player is offline, this method will not work as expected.
{% endhint %}
