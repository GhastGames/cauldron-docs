# Scoreboards
With VisualKit, it's easy to show scoreboards to players and update them without flickering.

### Creating a scoreboard

First, create an instance of CauldronScoreboard. Of course, you need the ``VisualKit`` dependency for this ([learn more](/docs/intro)). 

```java
CauldronScoreboard scoreboard = new CauldronScoreboard();
```

The scoreboard's lines are stored in instances of the ``ScoreboardValue`` class. To add a line, create a new ScoreboardValue:

```java
ScoreboardValue hello = new ScoreboardValue.fromString("§aHello!");
```

As you can see, color codes are supported. If you plan to update that line at runtime, you should set a reference. 

```java
ScoreboardValue hello = ScoreboardValue.fromString("§aHello!");
hello.setReference("line1");
```

Using the reference, you are able to access it in other parts of your plugin without knowing the line number.
Finally, you should set a title and then our scoreboard is ready.

```java
CauldronScoreboard scoreboard = new CauldronScoreboard();

ScoreboardValue hello = ScoreboardValue.fromString("§aHello!");
hello.setReference("line1");

scoreboard.setTitle(ScoreboardValue.fromString("§e§lSCOREBOARD")); // Title
```

To show it to a player, just use the ScoreboardManager:

```java
VisualKit.getInstance().getScoreboardManager().set(player, scoreboard);
```

### Updating a scoreboard

```java
ScoreboardValue update = ScoreboardValue.fromString("New value");
String reference = "The reference of the line you want to update";
update.setReference(reference);
update.id = manager.getByReference(reference, VisualKit.getInstance().getScoreboardManager()
                            .get(player).getContent()).id;
VisualKit.getInstance().getScoreboardManager().update(player, update);
```

You just need the reference of the line you want to update and the new content. 