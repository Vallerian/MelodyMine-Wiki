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

# unMute()

## `unMute` Method in `MelodyManager` Class

{% hint style="info" %}
The `unMute` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to unmute a player in the voice chat.
{% endhint %}

### Method Signature

```java
public void unMute(UUID uuid)
```

### Parameters

<table><thead><tr><th width="149">Parameter</th><th width="151">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>uuid</code></td><td><code>UUID</code></td><td>The UUID of the player to be unmuted.</td></tr></tbody></table>

### Usage

To use the `unMute` method, you need to have the UUID of the player you want to unmute. Here is an example of how to use this method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import org.bukkit.Bukkit;
import java.util.UUID;

public class ExamplePlugin {
    public void unmutePlayer(String playerName) {
        UUID playerUUID = Bukkit.getPlayer(playerName).getUniqueId();
        MelodyManager.INSTANCE.unMute(playerUUID);
        Bukkit.getLogger().info("Player " + playerName + " has been unmuted.");
    }
}
```

{% hint style="warning" %}
Make sure the player is currently muted before calling the `unMute` method. If the player is not muted, calling this method will have no effect.
{% endhint %}

In the above example, we first get the UUID of the player using Bukkit's `getPlayer` method. Then, we call the `unMute` method on the `MelodyManager` instance, passing in the player's UUID. Finally, we log a message to the console indicating that the player has been unmuted.
