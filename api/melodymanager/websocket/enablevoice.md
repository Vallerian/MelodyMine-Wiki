# enableVoice()

## `enableVoice` Method in `MelodyManager` Class

{% hint style="info" %}
The `enableVoice` method is a part of the `MelodyManager` class. This method is used to enable the voice feature for a player in the MelodyMine plugin.
{% endhint %}

### Method Signature

```java
public void enableVoice(String playerName, String playerUuid, String playerServer, String targetSocketID)
```

### Parameters

<table><thead><tr><th width="198">Parameter</th><th width="142">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>playerName</code></td><td><code>String</code></td><td>The name of the player for whom the voice feature is to be enabled.</td></tr><tr><td><code>playerUuid</code></td><td><code>String</code></td><td>The unique identifier (UUID) of the player.</td></tr><tr><td><code>playerServer</code></td><td><code>String</code></td><td>The server on which the player is currently playing.</td></tr><tr><td><code>targetSocketID</code></td><td><code>String</code></td><td>The socket ID of the target player.</td></tr></tbody></table>

### Example Usage

Below is an example of how to use the `enableVoice` method in another plugin.

```java
import ir.taher7.melodymine.core.MelodyManager;

public class ExamplePlugin {
    public void enableVoiceForPlayer() {
        // Assuming these values are obtained dynamically
        String playerName = "examplePlayer";
        String playerUuid = "exampleUuid";
        String playerServer = "exampleServer";
        String targetSocketID = "exampleSocketID";

        // Enable voice for the player
        MelodyManager.INSTANCE.enableVoice(playerName, playerUuid, playerServer, targetSocketID);

        // Log to console
        Bukkit.getLogger().info("Voice enabled for player: " + playerName + " to socketID: " + targetSocketID);
    }
}
```

{% hint style="warning" %}
Make sure to replace the example values with actual values when using this method.
{% endhint %}
