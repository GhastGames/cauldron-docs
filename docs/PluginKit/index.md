# PluginKit

To use PluginKit, initialize it in your plugin's main class:

```java
public class Plugin extends JavaPlugin {

    public void onEnable() {
        PluginKit.init(this);
    }
}
```