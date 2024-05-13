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

# renewData()

## `renewData` Method in `MelodyManager` Class

{% hint style="info" %}
The `renewData` method is used to update the data of a player in the MelodyMine plugin. This method sends the updated data to the client.
{% endhint %}

### Method Signature

```java
public void renewData(RenewData data)
```

### Parameters

<table><thead><tr><th width="143">Parameter</th><th width="161">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>data</code></td><td><code>RenewData</code></td><td>The updated data of the all players.</td></tr></tbody></table>

### Example

Here is an example of how to use the `renewData` method in another plugin:

```java
import ir.taher7.melodymine.core.MelodyManager;
import ir.taher7.melodymine.models.MelodyPlayer;
import ir.taher7.melodymine.models.RenewData;

public class ExamplePlugin {

    public void updatePlayerData(String playerUUID, RenewData newData) {
    
     MelodyManager.INSTANCE.renewData(newData);
     Bukkit.getLogger().info("Updating players data in client.");
  
    }
}
```

In this example, the `updatePlayerData` method in the `ExamplePlugin` class retrieves the `MelodyPlayer` instance for the player using their UUID. It then uses the `renewData` method of the `MelodyManager` class to update the player's data. If the data is successfully updated, a message is logged to the console. If the player is not found, a warning is logged instead.
