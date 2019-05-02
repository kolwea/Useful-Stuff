# Useful-Stuff
A list of functions and algorithms I find myself using or looking for constantly.


## Adding Css in Maven Project File
```Kotlin
val f = File("src/main/resources/AppStylesheet.css")
scene.stylesheets.add("file:///" + f.absolutePath.replace("\\", "/"))

```

## Building a Hexagon w/ center position & size

```Kotlin
    fun getHexPoint(i: Int): Pair<Double, Double> {
        var angledegree = 60 * i - 30.0
        var angleRadians = Math.PI / 180 * angledegree

        return Pair(centerX + size * Math.cos(angleRadians), centerY + size * Math.sin(angleRadians))
    }
    
   ```
   
 ## Distance
   
   ```javascript
    public static double distance(double x1, double y1, double x2, double y2) {
        double a = Math.pow((x2 - x1), 2);
        double b = Math.pow((y2 - y1), 2);
        return Math.sqrt(a + b);
    }
```

## Connect Two Node Shapes with a line JavaFX

   ```javascript
    public static Line connect(Shape one, Shape two) {
        Node n1 = one, n2 = two;
        Line line = null;
        if(one != null && two != null){
            line = new Line();
            line.setStrokeWidth(1);
            line.startXProperty().bind(Bindings.createDoubleBinding(() -> {
                Bounds b = n1.getBoundsInParent();
                return b.getMinX() + b.getWidth() / 2;
            }, n1.boundsInParentProperty()));

            line.startYProperty().bind(Bindings.createDoubleBinding(() -> {
                Bounds b = n1.getBoundsInParent();
                return b.getMinY() + b.getHeight() / 2;
            }, n1.boundsInParentProperty()));
            line.endXProperty().bind(Bindings.createDoubleBinding(() -> {
                Bounds b = n2.getBoundsInParent();
                return b.getMinX() + b.getWidth() / 2;
            }, n2.boundsInParentProperty()));
            line.endYProperty().bind(Bindings.createDoubleBinding(() -> {
                Bounds b = n2.getBoundsInParent();
                return b.getMinY() + b.getHeight() / 2;
            }, n2.boundsInParentProperty()));

        }
        return line;
    }
```

## Mapping one value range to another
   ```javascript
    public static double map(double value, double inMin, double inMax, double outMin, double outMax) {
        double done = outMin + ((outMax - outMin) / (inMax - inMin)) * (value - inMin);
        return done;
    }
```


## Adding Key Handlers to a JavaFX scene
   ```kotlin
   stage.addEventHandler(KeyEvent.KEY_PRESSED) { event ->
       when (event.code) {
           KeyCode.W -> println("W")
           else -> {}
       }
   }
```
## Binding Window title bar to Scene size
   ```kotlin
   stage.titleProperty().bind(
      scene.widthProperty().asString().concat(" : ")
           .concat(scene.heightProperty().asString()))
```

## setting Up A Timeline in JavaFX
   ```kotlin
    fun setupTimeline() {
        val event = EventHandler<ActionEvent> { update() }
        val keyframe = KeyFrame(Duration.millis(frameRate), event)
        timeline = Timeline(keyframe)
        timeline.cycleCount = Animation.INDEFINITE
    }
```

