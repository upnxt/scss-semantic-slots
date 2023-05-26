# SCSS semantic slots

Semantic slots allow labeling of CSS property values with context friendly notation e.g. `slot.get("body.text.primary")`

## Usage

**theme.scss**

```scss
@use "scss-semantic-slots" as slot;

$theme: (
    body: (
        background: #fff,
        text: (
            primary: #000,
            secondary: #ff0000,
        ),
    ),
);

@function get($key) {
    @return slot.map-slots($theme, $key);
}
```

**site.scss**

```scss
@use "theme" as theme;

body {
    background: theme.get("body.background");
    color: theme.get("body.text.primary");
}
```
