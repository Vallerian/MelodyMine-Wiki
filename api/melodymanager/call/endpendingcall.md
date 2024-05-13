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

# endPendingCall()

## `endPendingCall` Method in MelodyManager Class

{% hint style="info" %}
The `endPendingCall` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to end a pending call between two players in the MelodyMine system. It takes two `MelodyPlayer` objects as parameters, representing the two players involved in the call.
{% endhint %}

### Method Signature

In Java, the method signature would look like this:

```java
public void endPendingCall(MelodyPlayer melodyPlayer, MelodyPlayer targetPlayer)
```

### Parameters

<table><thead><tr><th width="203">Parameter</th><th width="192">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>melodyPlayer</code></td><td><code>MelodyPlayer</code></td><td>The first player involved in the call.</td></tr><tr><td><code>targetPlayer</code></td><td><code>MelodyPlayer</code></td><td>The second player involved in the call.</td></tr></tbody></table>

### Usage

To use this method in another plugin, you would first need to get instances of the `MelodyPlayer` objects for the two players. You can do this using the `getMelodyPlayer` and `getMelodyPlayerFromSocketID` methods in the `MelodyManager` class.

Here is an example of how you might use this method in a Java class:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;
import org.bukkit.Bukkit;

public class ExampleClass {

    public void endCallExample(String playerUUID, String targetPlayerUUID) {
        MelodyPlayer player = MelodyManager.INSTANCE.getMelodyPlayer(playerUUID);
        MelodyPlayer targetPlayer = MelodyManager.INSTANCE.getMelodyPlayer(targetPlayerUUID);

        if (player != null && targetPlayer != null) {
            MelodyManager.INSTANCE.endPendingCall(player, targetPlayer);
            Bukkit.getLogger().info("Pending call between " + player.getName() + " and " + targetPlayer.getName() + " has been ended.");
        }
    }
}
```

In this example, `endCallExample` is a method that takes the UUIDs of two players as strings. It retrieves the `MelodyPlayer` objects for these players using the `getMelodyPlayer` method, and then uses the `endPendingCall` method to end any pending call between them. If the call is successfully ended, a message is printed to the console.

{% hint style="warning" %}
Remember to check that the `MelodyPlayer` objects are not null before calling `endPendingCall`. If either of the players does not exist in the MelodyMine system, `getMelodyPlayer` will return null.
{% endhint %}
