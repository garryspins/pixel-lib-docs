- [Blur](#blur)
- [Circle](#circle)
- [Overheads](#overheads)
- [Rounded](#rounded)
- [Text](#text)

<a name="blur"></a>
## Blur
TBD
<br/>

<a name="circle"></a>
## Circle
PIXELLib provides functions for drawing cashed and uncashed circles

###PIXEL.CreateCircle(x, y, ang, sec, pct, rad)
 - Returns the created poly table for passing to DrawPoly
```php.line-numbers lua
    local circle = PIXEL.CreateCircle(50, 50, 180, 32, 370, 400)
    hook.Add("HUDPaint", "PIXEL.Lib.Test", function() 
        surface.DrawPoly(circle)
    end)
```

###PIXEL.DrawCircleUncached(x, y, ang, sec, pct, rad)
- Draws a circle
```php.line-numbers lua
    hook.Add("HUDPaint", "PIXEL.Lib.Test", function() 
        PIXEL.DrawCircleUncached(50, 50, 180, 32, 370, 400)
    end)
```

<br/>
<a name="overheads"></a>
## Overheads

###PIXEL.ShouldDrawUI(ent)
- Checks if an entity is close enough to render its 3d2d
- Used internally for the overheads
```php.line-numbers lua
    function ENT:Draw()
        self:DrawModel()
        if not PIXEL.ShouldDrawUI(self) then return end
        //your custom 3d2d
    end
```

###PIXEL.DrawOverheadEx(ent, text, image?, angle?, pos?, scale?)
- Draws a 3d2d overhead
- Internal function used by drawentoverhead and drawnpcoverhead

###PIXEL.DrawEntOverhead(ent, text, image?, angle?, pos?, scale?)
- Checks if an entity is close enough to render its 3d2d
- Used internally for the overheads
```php.line-numbers lua
    function ENT:Draw()
        self:DrawModel()
        PIXEL.DrawEntOverhead(self, "Fuel Barrel")
    end
```

###PIXEL.DrawEntOverhead(ent, text, image?, angle?, pos?, scale?)
- Draws a 3d2d overhead, for a prop based entity
```php.line-numbers lua
    function ENT:Draw()
        self:DrawModel()
        PIXEL.DrawEntOverhead(self, "Fuel Barrel")
    end
```

###PIXEL.DrawNPCOverhead(ent, text, image?, angle?, pos?, scale?)
- Draws a 3d2d overhead, for a npc based entity
```php.line-numbers lua
    function ENT:Draw()
        self:DrawModel()
        PIXEL.DrawNPCOverhead(self, "Fuel Buyer")
    end
```

<br/>
<a name="rounded"></a>
## Rounded
Currently these are just pointers to normal draw functions, eventually these
will be replaced by more optimized versions of these functions

###PIXEL.DrawRoundedBox(rounding, x, y, w, h, color)
- Draws a rounded box

###PIXEL.DrawRoundedBoxEx(rounding, x, y, w, h, color, roundTopLeft?, roundTopRight?, roundBottomLeft?, roundBottomRight?)
- Draws a rounded box with the ability of setting what corners to round

###PIXEL.DrawFullRoundedBox(rounding, x, y, w, h, color)
- Pointer to PIXEL.DrawRoundedBox

###PIXEL.DrawFullRoundedBoxEx(rounding, x, y, w, h, color, roundTopLeft?, roundTopRight?, roundBottomLeft?, roundBottomRight?)
- Pointer to PIXEL.DrawRoundedBoxEx

<br/>
<a name="text"></a>
## Text
PIXELLib provides a few functions to make drawing text a bit more simple

###PIXEL.DrawText(text, font, x, y, col, xal?, yal?)
- Draws text, with the option to y or x align
```php.line-numbers lua
    local font = PIXEL.GetFont(40)
    hook.Add("HUDPaint", "PIXEL.Lib.Test", function()
        PIXEL.DrawText("Hello!!", font, 0, 0, PIXEL.Colors.PrimaryText)
    end)
```

###PIXEL.CroppedText(text, font, width)
- Draws text, and allows you to add a cutoff point to stop overflow off the screen/panel
```php.line-numbers lua
    local font = PIXEL.GetFont(40)
    hook.Add("HUDPaint", "PIXEL.Lib.Test", function()
        PIXEL.DrawText(PIXEL.CroppedText("Helloooooooo", font, 100), font, 0, 0, PIXEL.Colors.PrimaryText)
    end)
```

