# Command Builder

> 🚨 Don't forget to mention your plugin's commands in the plugin.yml. Read more [here](https://www.spigotmc.org/wiki/plugin-yml/).

With PluginKit, it's easy to create commands and skip boilerplate code. You can use the ``DynamicCommandBuilder``. First, you need an instance of ``DynamicCommandBuilder``. We recommend to register the commands in your plugin's ``onEnable`` method.

```java
DynamicCommandBuilder command = new DynamicCommandBuilder("hello")
                .register();
```

The constructor's argument is the command, for example ``hello`` for a ``/hello`` command. Now you can set an executor:

```java
DynamicCommandBuilder command = new DynamicCommandBuilder("hello")
                .setExecutor(details -> {
                    details.getSender().sendMessage("hi");
                    return true;
                })
                .register();
```

### Conditions

To only execute the command when a condition is fullfilled, you can set a condition:

```java
DynamicCommandBuilder command = new DynamicCommandBuilder("hello")
                .setCondition((sender, args) -> new ConditionResponse((sender.getName().equals("GhastAdmin")), "§cYou are not GhastAdmin"))
                .setExecutor(details -> {
                    details.getSender().sendMessage("hi");
                    return true;
                })
                .register();
```

With that condition, the command will only be executed when the sender's name is ``GhastAdmin``. If that's not the case, a message is sent.

### Player-only

Using the ``setPlayerOnly`` method, you can set the command to player-only (cannot be executed by the console).

```java
DynamicCommandBuilder command = new DynamicCommandBuilder("hello")
                .setExecutor(details -> {
                    details.getSender().sendMessage("hi");
                    return true;
                })
                .setPlayerOnly(true)
                .register();
```

### Permissions

If you want only users with a permission to execute the command, use the ``setPermission`` and ``setNoPermissionMessage`` methods.

```java
DynamicCommandBuilder command = new DynamicCommandBuilder("hello")
                .setExecutor(details -> {
                    details.getSender().sendMessage("hi");
                    return true;
                })
                .setPlayerOnly(true)
                .setPermission("test.hello")
                .setNoPermissionMessage("§cNo permission")
                .register();
```

