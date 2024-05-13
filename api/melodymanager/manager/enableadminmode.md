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

# enableAdminMode()

## `enableAdminMode` Method in `MelodyManager` Class

{% hint style="info" %}
The `enableAdminMode` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to enable the admin mode for a specific player in the client.
{% endhint %}

### Method Signature

```java
public void enableAdminMode(String uuid)
```

### Parameters

<table><thead><tr><th width="148">Parameter</th><th width="135">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>uuid</code></td><td><code>String</code></td><td>The unique identifier of the player for whom the admin mode is to be enabled.</td></tr></tbody></table>

### Usage

To use this method in other plugins, you need to import the `MelodyManager` class and call the `enableAdminMode` method on its instance. Here is an example:

```java
import ir.taher7.melodymine.core.MelodyManager;

public class ExamplePlugin {
    public void enableAdminForPlayer(String uuid) {
        MelodyManager.INSTANCE.enableAdminMode(uuid);
        Bukkit.getLogger().info("Admin mode enabled for player with UUID: " + uuid);
    }
}
```

In the above example, we have a method `enableAdminForPlayer` in our `ExamplePlugin` class. This method takes a player's UUID as a parameter and enables the admin mode for that player using the `enableAdminMode` method from `MelodyManager`. It then logs a message to the console indicating that the admin mode has been enabled for the player.

{% hint style="warning" %}
Make sure that the UUID passed to the `enableAdminMode` method is valid and corresponds to a player in the server. Invalid UUIDs will not have any effect.
{% endhint %}
