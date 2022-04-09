---
sidebar_position: 1
---

# Getting started

<details>
<summary>What is Cauldron?</summary>
Cauldron is a collection of libraries for Minecraft servers and their plugins. With these libraries, you can simplify your development workflow. You don't even have to install a plugin on your server!
</details>

Getting started with Cauldron is easy. First, you need a Java or Kotlin project (with Maven) and a running Minecraft server with version 1.8.8. Support for newer versions is planned. 

### Step 1: Add Spigot dependency

Add the ``spigot-api`` dependency to your ``pom.xml``

```xml
<dependencies>
    <dependency>
           <groupId>org.spigotmc</groupId>
           <artifactId>spigot-api</artifactId>
           <version>1.8.8-R0.1-SNAPSHOT</version>
           <scope>provided</scope>
    </dependency>
</dependencies>

<repositories>
    <repository>
        <id>spigot-repo</id>
        <url>https://hub.spigotmc.org/nexus/content/repositories/snapshots/</url>
    </repository>
</repositories>
```

### Step 2: Add Cauldron dependencies

Now you have access to the Spigot API within your project. To use Cauldron, you have to include its dependency as well. The different Cauldron modules you want to use have to be included seperately. First, add the GhastGames Public Repository to your ``<repositories>`` tag in the pom.xml:

```xml
<repository>
  <id>ghastgames-public</id>
  <name>GhastGames Public Repository</name>
  <url>https://repo.ghastgames.net/snapshots</url>
</repository>
```

Then, add the modules you need. For most features, you'll need PluginKit. Just add the other dependencies when you need them. The needed modules are mentioned in all guides in this documentation.

```xml
<!-- PluginKit -->
<dependency>
  <groupId>net.ghastgames.cauldron</groupId>
  <artifactId>pluginkit</artifactId>
  <version>1.0-SNAPSHOT</version>
</dependency>

<!-- VisualKit -->
<dependency>
  <groupId>net.ghastgames.cauldron</groupId>
  <artifactId>visualkit</artifactId>
  <version>1.0-SNAPSHOT</version>
</dependency>

<!-- StorageKit -->
<dependency>
  <groupId>net.ghastgames.cauldron</groupId>
  <artifactId>storagekit</artifactId>
  <version>1.0-SNAPSHOT</version>
</dependency>
```

Since CloudKit isn't ready yet, you can't use it in your project yet. Join our (Discord)[https://dc.ghastgames.net] to get notified when it's ready!