- [Blur](#blur)
- [Circle](#circle)
- [Scale](#scale)
- [Color](#color)

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
