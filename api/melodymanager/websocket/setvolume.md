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

# setVolume()

## `setVolume` Method in `MelodyManager` Class

{% hint style="info" %}
The `setVolume` method is a part of the `MelodyManager` class. It is used to set the volume for a specific player in the game. The volume level is determined based on the player's location and the target's location.
{% endhint %}

### Method Signature

```java
public void setVolume(String playerUuid, String targetSocketID, Location playerLocation, Location targetLocation)
```

### Parameters

<table><thead><tr><th width="204">Parameter</th><th width="167">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>playerUuid</code></td><td><code>String</code></td><td>The UUID of the player for whom the volume is to be set.</td></tr><tr><td><code>targetSocketID</code></td><td><code>String</code></td><td>The socket ID of the target player.</td></tr><tr><td><code>playerLocation</code></td><td><code>Location</code></td><td>The current location of the player.</td></tr><tr><td><code>targetLocation</code></td><td><code>Location</code></td><td>The current location of the target player.</td></tr></tbody></table>

### Example

Here is an example of how to use the `setVolume` method in another plugin:

```java
import org.bukkit.Location;
import org.bukkit.entity.Player;
import ir.taher7.melodymine.core.MelodyManager;

public class ExamplePlugin {

    public void adjustPlayerVolume(Player player, Player target) {
        String playerUuid = player.getUniqueId().toString();
        String targetSocketID = target.getUniqueId().toString(); // Assuming the target's UUID is used as the socket ID
        Location playerLocation = player.getLocation();
        Location targetLocation = target.getLocation();

        MelodyManager.INSTANCE.setVolume(playerUuid, targetSocketID, playerLocation, targetLocation);

        Bukkit.getLogger().info("Set volume for player " + player.getName() + " based on location of target player " + target.getName());
    }
}
```

In this example, the `adjustPlayerVolume` method retrieves the UUIDs and locations of the player and target, and then uses these values to call the `setVolume` method. After the volume is set, a message is logged to the console.
