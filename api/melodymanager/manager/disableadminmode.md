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

# disableAdminMode()

## `disableAdminMode` Method in `MelodyManager` Class

{% hint style="info" %}
The `disableAdminMode` method is a part of the `MelodyManager` class in the MelodyMine plugin. This method is used to disable the admin mode for a specific player in the MelodyMine plugin.
{% endhint %}

### Method Signature

```java
public void disableAdminMode(String uuid)
```

### Parameters

<table><thead><tr><th width="153">Parameter</th><th width="111">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>uuid</code></td><td><code>String</code></td><td>The unique identifier of the player for whom the admin mode is to be disabled.</td></tr></tbody></table>

### Usage

To use this method in other plugins, you need to import the `MelodyManager` class and call the `disableAdminMode` method on its instance. Here is an example:

```java
import ir.taher7.melodymine.core.MelodyManager;

public class ExamplePlugin {
    public void disableAdminForPlayer(String uuid) {
        MelodyManager.INSTANCE.disableAdminMode(uuid);
        Bukkit.getLogger().info("Admin mode disabled for player with UUID: " + uuid);
    }
}
```

In this example, the `disableAdminForPlayer` method in the `ExamplePlugin` class disables the admin mode for a player with a specific UUID and logs this action to the console.

{% hint style="warning" %}
Make sure that the UUID passed to the `disableAdminMode` method is valid and corresponds to a player who is currently in admin mode. Otherwise, the method may not have the desired effect.
{% endhint %}
