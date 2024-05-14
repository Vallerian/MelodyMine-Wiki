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
