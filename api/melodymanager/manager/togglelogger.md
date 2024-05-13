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

# toggleLogger()

## `toggleLogger` Method in `MelodyManager` Class

{% hint style="info" %}
The `toggleLogger` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to toggle the message log for a specific player in the game. The method takes a single parameter, the UUID of the player, and toggles the logger for that player.
{% endhint %}

### Method Signature

```java
public void toggleLogger(String uuid)
```

### Parameters

<table><thead><tr><th width="129">Parameter</th><th width="137">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>uuid</code></td><td><code>String</code></td><td>The UUID of the player for whom the logger is to be toggled.</td></tr></tbody></table>

### Usage

To use the `toggleLogger` method in your plugin, you need to import the `MelodyManager` class and call the method on its instance. Here is an example:

```java
import ir.taher7.melodymine.core.MelodyManager;

public class ExamplePlugin {
    public void togglePlayerLogger(String playerUUID) {
        MelodyManager.INSTANCE.toggleLogger(playerUUID);
        Bukkit.getLogger().info("Toggled logger for player with UUID: " + playerUUID);
    }
}
```

In this example, the `togglePlayerLogger` method in the `ExamplePlugin` class calls the `toggleLogger` method on the `MelodyManager` instance. It then logs a message to the console indicating that the logger has been toggled for the player with the given UUID.

{% hint style="warning" %}
Make sure to replace `playerUUID` with the actual UUID of the player for whom you want to toggle the logger.
{% endhint %}
