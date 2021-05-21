- [Frame](#frame)
- [Button](#button)
- [Checkbox](#Checkbox)
- [Color Picker](#colorpicker)
- [Slider](#slider)
- [Sidebar](#sidebar)
- [Tabs](#tabs)

<a name="frame"></a>
## PIXEL.Frame
Base frame

###PANEL:SetTitle(title)
- Sets the panel's header title

###PANEL:SetImage(imgurid)
- Sets the panel's header image

###PANEL:CreateSidebar()
- Creates a sidebar on the panel

<br/>
<a name="button"></a>
## PIXEL.Button
General button panel, can be used as just a image or a text button

###PANEL:SetFont(font)
- Sets the buttons font if using text

###PANEL:SetText(text)
- Sets the buttons text, set to false for an image button

###PANEL:SetImage(imgurid)
- Sets the buttons image

###PANEL:SizeToText(pad)
- Sets the buttons padding on each side of the text

###PANEL:DoClick()
- Function for you to override for whatever events you want

###PANEL:DoRightClick()
- Function for you to override for whatever events you want

<br/>
<a name="checkbox"></a>
## PIXEL.Checkbox
A simple toggleable checkbox element

###PANEL:SetText(text)
- Sets the checkbox label

###PANEL:SetChecked(bool)
- Sets the checkbox state

###PANEL:GetChecked()
- Returns the checkbox state

<br/>
<a name="colorpicker"></a>
## PIXEL.ColorPicker
A set of 3 sliders to make up a RGB Color

###PANEL:GetColor()
- Returns the currect color

###PANEL:SetColor(color)
- Sets the current color

###PANEL:OnColorChanged(color)
- Function for you to override for whatever events you want

<br/>
<a name="slider"></a>
## PIXEL.Slider
A simple slider

###PANEL:SetBGCol(Color)
- Set the bar background color

###PANEL:GetPercentage(num)
- Returns the percentage of the number passed

###PANEL:SetPercentage(num)
- Sets the percentage based on the number passed

###PANEL:OnValueChanged()
- Function for you to override for whatever events you want

<br/>
<a name="navbar"></a>
## PIXEL.Navbar
TBW

<br/>
<a name="sidebar"></a>
## PIXEL.Sidebar
TBW

<br/>
<a name="tabs"></a>
## PIXEL.Tabs
TBW



