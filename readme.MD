All i did was make it be able to go wider. ok bye

the changes are just those in `java/me/redcarlos/higtools/modules/main/HighwayBuilderHIG.java`

```java
    private final Setting<Integer> width = sgGeneral.add(new IntSetting.Builder()
            .name("width")
            .description("Width of the highway.")
            .defaultValue(7)
            .range(1, 9)
            .sliderRange(1, 9)
            .build()
    );
```

```java
    private int getWidthLeft() {
        return switch (width.get()) {
            case 2, 3 -> 1;
            case 4, 5 -> 2;
            case 6, 7, 8 -> 3;
            case 9 -> 4;
            default -> 0;
        };
    }

    private int getWidthRight() {
        return switch (width.get()) {
            case 3, 4 -> 1;
            case 5, 6 -> 2;
            case 7, 8 -> 3;
            case 9 -> 4;
            default -> 0;
        };
    }
```
