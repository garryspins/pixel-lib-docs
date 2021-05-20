- [Fonts](#fonts)
- [Images](#images)
- [Scale](#scale)

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

<a name="images"></a>
## Images
PIXELLib provides helper functions to draw images from imgur<br/>
The spinner image will automatically be downloaded when PIXELLib is loaded.

###PIXEL.ImgurDL(id)
- Returns the material of the downloaded imgur ID
- Don't cache the return value, because the function will return a spinner icon until the image is downloaded
```php.line-numbers lua
    hook.Add("HUDPaint", "PIXEL.Lib.Test", function() 
        surface.SetDrawColor(color_white)
        surface.SetMaterial(PIXEL.ImgurDL("C9Sm90a"))
        surface.DrawTexturedRect(0, 0, 512, 512)
    end)
```

###PIXEL.DrawImgur(x, y, w, h, id)
- Will draw a spinner icon until the image is downloaded
```php.line-numbers lua
    hook.Add("HUDPaint", "PIXEL.Lib.Test", function()
        surface.SetDrawColor(color_white)
        PIXEL.DrawImgur(0, 0, 512, 512, "C9Sm90a")
    end)
```

<a name="scale"></a>
## Scale
PIXELLib provides functions to scale with ease

### PIXEL.Scale(sz)
- Returns the size scaled based on screen height
```php.line-numbers lua
    hook.Add("HUDPaint", "PIXEL.Lib.Test", function()
        local imageSize = PIXEL.Scale(512)
        surface.SetDrawColor(color_white)
        PIXEL.DrawImgur(0, 0, imageSize, imageSize, "C9Sm90a")
    end)
```

###PIXEL.ScaleH(sz)
- Pointer to PIXEL.Scale

###PIXEL.ScaleW(sz)
- Returns the size scaled based on screen width

