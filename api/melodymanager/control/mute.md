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

# mute()

## `Mute` Method in `MelodyManager` Class

{% hint style="info" %}
The `mute` method in the `MelodyManager` class is used to mute a player in the MelodyMine plugin. This method takes the UUID of the player as a parameter and performs the mute operation.
{% endhint %}

### Method Signature

```java
public void mute(String uuid)
```

### Parameters

<table><thead><tr><th width="118">Parameter</th><th width="168">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>uuid</code></td><td><code>String</code></td><td>The UUID of the player to be muted.</td></tr></tbody></table>

### Usage

To use the `mute` method in your plugin, you need to import the `MelodyManager` class and use its instance to call the method. Here is an example:

```java
import ir.taher7.melodymine.core.MelodyManager;

public class YourPluginClass {
    public void someMethod() {
        // Get the instance of MelodyManager
        MelodyManager melodyManager = MelodyManager.INSTANCE;

        // Get the UUID of the player to be muted
        String playerUUID = "player-uuid-goes-here";

        // Mute the player
        melodyManager.mute(playerUUID);

        // Print a message to the console
        Bukkit.getLogger().info("Player with UUID " + playerUUID + " has been muted.");
    }
}
```

{% hint style="warning" %}
Make sure to replace `"player-uuid-goes-here"` with the actual UUID of the player you want to mute.
{% endhint %}
