# ⚙️ Usage

## MelodyMine API Usage

To integrate the MelodyMine API, you can utilize the following methods in relation to your own plugin.

## Maven

```xml
<repository>
  <id>repo-sayandevelopment-snapshots</id>
  <name>SayanDevelopment Repository</name>
  <url>https://repo.sayandev.org/snapshots</url>
</repository>
```

```xml
<dependency>
  <groupId>ir.taher7</groupId>
  <artifactId>melodymine</artifactId>
  <version>2.0.0-SNAPSHOT</version>
</dependency>
```

***

## Gradle

### Groovy

```groovy
repositories {
    maven {
        name = "sayandevelopment-repo"
        url = "https://repo.sayandev.org/snapshots"
    }
}
```

```groovy
dependencies {
    compileOnly "ir.taher7:melodymine:2.0.0-SNAPSHOT"
}
```

### Kotlin

<pre class="language-kotlin"><code class="lang-kotlin">repositories {
<strong>    maven("https://repo.sayandev.org/snapshots")
</strong>}
</code></pre>

```kotlin
dependencies {
    compileOnly("ir.taher7:melodymine:2.0.0-SNAPSHOT")
}
```

***

## MelodyManager

You can view all the methods of the MelodyMine Manager from the following page:

{% content-ref url="melodymanager/" %}
[melodymanager](melodymanager/)
{% endcontent-ref %}

## MelodyMine Events

You can view all the Events of the MelodyMine Manager from the following page:

{% content-ref url="events/" %}
[events](events/)
{% endcontent-ref %}

***

## MelodyPhone

One of the plugins built with the MelodyMine API is MelodyPhone, which is entirely constructed to utilize [API calls](melodymanager/call/) from MelodyMine.

{% hint style="info" %}
&#x20;If you have any questions regarding this plugin or any inquiries related to it, feel free to join the [MelodyMine Discord server](https://discord.gg/CBua8YectX) and ask.
{% endhint %}

{% embed url="https://cdn.discordapp.com/attachments/1169951231976939643/1174391871385120830/2023-11-15_20-07-19.mp4?ex=66439729&hm=2071462783835d2805114e489e1381e207c29d720c6d1bfff3f0fa9191be845a&is=664245a9" %}

***

## MelodyRadio

Another plugin developed with the MelodyMine API is MelodyRadio, which extensively utilizes the Sound API of MelodyMine.

&#x20;This plugin serves as an addon for the [VehiclesPlus](https://www.spigotmc.org/resources/vehiclesplus-1-12-1-20-4.70523/) plugin, enabling the addition of radio functionality to vehicles within that plugin.&#x20;

Additionally, it leverages the [World Guard](https://enginehub.org/worldguard) API, allowing players to broadcast any sound or music stream within or outside a specified region.

{% hint style="info" %}
If you have any inquiries regarding this plugin or need assistance, feel free to join the [MelodyMine Discord server](https://discord.gg/CBua8YectX) and ask.
{% endhint %}

{% embed url="https://cdn.discordapp.com/attachments/983568272622506014/1226200598936944802/MelodyRadio.mp4?ex=66438b4c&hm=32c82391ac0db820fc74f084925aa2af18fb53d7cd6fcc091f36a44fc92ad9d6&is=664239cc" %}
