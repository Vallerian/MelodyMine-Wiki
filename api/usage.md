# ⚙️ Usage

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
  <version>2.0.0</version>
</dependency>
```

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
    compileOnly "ir.taher7:melodymine:2.0.0"
}
```

### Kotlin

<pre class="language-kotlin"><code class="lang-kotlin">repositories {
<strong>    maven("https://repo.sayandev.org/snapshots")
</strong>}
</code></pre>

```kotlin
dependencies {
    compileOnly("ir.taher7:melodymine:2.0.0")
}
```
