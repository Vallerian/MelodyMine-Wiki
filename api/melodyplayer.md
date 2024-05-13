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

# 👨 MelodyPlayer

## `MelodyPlayer` Class

{% hint style="info" %}
The `MelodyPlayer` class is a data class in Kotlin that represents a player in the MelodyMine system. It contains various properties related to the player's state and actions in the system.
{% endhint %}

### Properties

<table><thead><tr><th width="221">Property</th><th width="211">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>player</code></td><td><code>Player?</code></td><td>The Bukkit player object.</td></tr><tr><td><code>id</code></td><td><code>Int</code></td><td>The unique identifier of the player in the system.</td></tr><tr><td><code>uuid</code></td><td><code>String</code></td><td>The UUID of the player.</td></tr><tr><td><code>name</code></td><td><code>String</code></td><td>The name of the player.</td></tr><tr><td><code>server</code></td><td><code>String</code></td><td>The server that the player is currently connected to.</td></tr><tr><td><code>socketID</code></td><td><code>String?</code></td><td>The ID of the socket connection for the player.</td></tr><tr><td><code>verifyCode</code></td><td><code>String?</code></td><td>The verification code for the player.</td></tr><tr><td><code>isActiveVoice</code></td><td><code>Boolean</code></td><td>Indicates whether the player's voice is active.</td></tr><tr><td><code>serverIsOnline</code></td><td><code>Boolean</code></td><td>Indicates whether the server is online.</td></tr><tr><td><code>webIsOnline</code></td><td><code>Boolean</code></td><td>Indicates whether the web interface is online.</td></tr><tr><td><code>adminMode</code></td><td><code>Boolean</code></td><td>Indicates whether the player is in admin mode.</td></tr><tr><td><code>isMute</code></td><td><code>Boolean</code></td><td>Indicates whether the player is muted.</td></tr><tr><td><code>isToggle</code></td><td><code>Boolean</code></td><td>Indicates whether the toggle state is on or off.</td></tr><tr><td><code>isSelfMute</code></td><td><code>Boolean</code></td><td>Indicates whether the player has muted themselves.</td></tr><tr><td><code>isDeafen</code></td><td><code>Boolean</code></td><td>Indicates whether the player is deafened.</td></tr><tr><td><code>isInCall</code></td><td><code>Boolean</code></td><td>Indicates whether the player is in a call.</td></tr><tr><td><code>callTarget</code></td><td><code>MelodyPlayer?</code></td><td>The player that the current player is in a call with.</td></tr><tr><td><code>isCallPending</code></td><td><code>Boolean</code></td><td>Indicates whether there is a pending call for the player.</td></tr><tr><td><code>callPendingTarget</code></td><td><code>MelodyPlayer?</code></td><td>The player that the current player has a pending call with.</td></tr><tr><td><code>callToggle</code></td><td><code>Boolean</code></td><td>Indicates whether the call toggle state is on or off.</td></tr><tr><td><code>isStartCall</code></td><td><code>Boolean</code></td><td>Indicates whether the player has started a call.</td></tr><tr><td><code>pendingTask</code></td><td><code>BukkitTask?</code></td><td>The pending task for the player.</td></tr><tr><td><code>isTalk</code></td><td><code>Boolean</code></td><td>Indicates whether the player is talking.</td></tr><tr><td><code>talkBossBar</code></td><td><code>TalkBossBar?</code></td><td>The boss bar for the player.</td></tr><tr><td><code>talkNameTag</code></td><td><code>TalkNameTag?</code></td><td>The name tag for the player.</td></tr><tr><td><code>isSendOffer</code></td><td><code>ArrayList&#x3C;String></code></td><td>The list of offers that the player has sent.</td></tr></tbody></table>

### Example Usage

{% hint style="info" %}
Here is an example of how to use the `MelodyPlayer` class in a Java plugin.
{% endhint %}

```java
import ir.taher7.melodymine.models.MelodyPlayer;
import ir.taher7.melodymine.storage.Storage;
import org.bukkit.Bukkit;
import org.bukkit.entity.Player;

public class ExamplePlugin {

    public void printPlayerInfo(String uuid) {
        MelodyPlayer melodyPlayer = Storage.INSTANCE.onlinePlayers.get(uuid);
        if (melodyPlayer != null) {
            Player player = melodyPlayer.getPlayer();
            Bukkit.getLogger().info("Player ID: " + melodyPlayer.getId());
            Bukkit.getLogger().info("Player UUID: " + melodyPlayer.getUuid());
            Bukkit.getLogger().info("Player Name: " + melodyPlayer.getName());
            Bukkit.getLogger().info("Player Server: " + melodyPlayer.getServer());
            // Add more properties as needed
        } else {
            Bukkit.getLogger().info("Player not found");
        }
    }
}
```

In this example, the `printPlayerInfo` method retrieves a `MelodyPlayer` object from the `Storage` class using a UUID, and then prints various properties of the `MelodyPlayer` to the console.

### Using `MelodyManager` to get `MelodyPlayer`

{% hint style="info" %}
Here is an example of how to use the `getMelodyPlayer` and `getMelodyPlayerFromSocketID` methods from `MelodyManager` class in a Java plugin.
{% endhint %}

```java
import ir.taher7.melodymine.models.MelodyPlayer;
import ir.taher7.melodymine.manager.MelodyManager;
import org.bukkit.Bukkit;

public class ExamplePlugin {

    public void printPlayerInfoFromManager(String uuid, String socketID) {
        MelodyPlayer melodyPlayerFromUUID = MelodyManager.INSTANCE.getMelodyPlayer(uuid);
        MelodyPlayer melodyPlayerFromSocketID = MelodyManager.INSTANCE.getMelodyPlayerFromSocketID(socketID);
        
        if (melodyPlayerFromUUID != null) {
            Bukkit.getLogger().info("Player ID from UUID: " + melodyPlayerFromUUID.getId());
        } else {
            Bukkit.getLogger().info("Player not found from UUID");
        }

        if (melodyPlayerFromSocketID != null) {
            Bukkit.getLogger().info("Player ID from SocketID: " + melodyPlayerFromSocketID.getId());
        } else {
            Bukkit.getLogger().info("Player not found from SocketID");
        }
    }
}
```

In this example, the `printPlayerInfoFromManager` method retrieves a `MelodyPlayer` object from the `MelodyManager` class using a UUID and a SocketID, and then prints the ID of the `MelodyPlayer` to the console.
