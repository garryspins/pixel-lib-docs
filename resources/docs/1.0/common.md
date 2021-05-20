- [Fonts](#fonts)

<a name="fonts"></a>
## Fonts
PIXELLIb internally caches fonts based on size and weight. All fonts are Open Sans SemiBold

### PIXEL.GetFont(size, weight?)
 - Returns font string
 - Scales based on screen resolution
```php.line-numbers lua
    local font = PIXEL.GetFont(100)

    hook.Add("HUDPaint", "PIXEL.Lib.Test", function() 
        PIXEL.DrawText("Hello!", font, 0, 0, PIXEL.Colors.PrimaryText)
    end)
```

### PIXEL.GetFontUnscaled(size, weight?)
- Returns font string
```php.line-numbers lua
    local font = PIXEL.GetFontUnscaled(100)

    hook.Add("HUDPaint", "PIXEL.Lib.Test", function() 
        PIXEL.DrawText("Hello!", font, 0, 0, PIXEL.Colors.PrimaryText)
    end)
```

### PIXEL.SetFont(font)
- Set the current font to be used for text operations later.
```php.line-numbers lua
    local font = PIXEL.GetFont(100)
    PIXEL.SetFont(font)
```

### PIXEL.GetTextSize(text, font)
- Calculates w, h of the text passed based on the font.
```php.line-numbers lua
    local font = PIXEL.GetFont(100)
    local string = "lmao"

    local w, h = PIXEL.GetTextSize(string, font)
    print(w .. " " .. h)
```
