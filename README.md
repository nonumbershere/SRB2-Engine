# SRB2-Editor
The best hack for SRB2.


# Source Code
```lua
local a = getAddressList()
form1 = getMainForm()
split = createSplitter(getMainForm())
split.Align = alRight
panel1 = createPanel(getMainForm())
panel1.Width = 180
panel1.Align = alRight
panel1.Caption = ''
about = createLabel(panel1)
about.caption = "This is a cheat for SRB2."
about.top = 90
about.font.height = 20
credits = createMenu
function cycleFullCompact(sender,force) getMainForm().Splitter1.Visible = state; getMainForm().Panel4.Visible    = state; getMainForm().Panel5.Visible = state; end; function addCompactMenu() if compactmenualreadyexists then return end; local parent = getMainForm().Menu.Items; compactmenualreadyexists = 'yes'; end; addCompactMenu(); cycleFullCompact(nil,true)
form1.caption = "SRB2 Hack V2"
form1.color = "$00FF2F2F"
form1.height = 500
form1.BorderStyle = "bsSingle"
form1.Position = "poDesktopCenter"
inject = createButton(panel1)
inject.Left = 15
inject.Height = 70
inject.Hint = 'Restart Cheat Engine\nto attach'
inject.Top = 10
inject.Width = 150
inject.Caption = 'Attach'
inject.ShowHint = false
inject.onclick = function()
 if openProcess("srb2win.exe") == null then
showMessage("Please Start SRB2.")
 else
openProcess("srb2win.exe")
inject.enabled = false
inject.caption = 'injected'
 end
end
inject.font.height = 50
if openProcess("srb2win.exe") == null then

  else
openProcess("srb2win.exe")
inject.enabled = false
inject.caption = 'Injected'
end
local rings = a.getMemoryRecordByDescription("Rings")
function UDF1_CEButton1Click(sender)
  if openProcess("srb2win.exe") == null then
     showMessage("Please Install OR Start SRB2. Thank you!")
   else
    showMessage("Injected!")
    openProcess("srb2win.exe")
  end
end
local int = getInternet()
local ICO = int.getURL("http://www.icons101.com/icons/48/Game_Stars_by_Yellow_Icon_Design/128/Sonic.png")
local IM = createStringStream(ICO)
int.Destroy()
local Pic = createPicture()
Pic.loadFromStream(IM)
local Bit = Pic.getBitmap()
getApplication().Icon = Bit
local slowmo = a.getMemoryRecordByDescription("SlowMo")
function UDF1_CECheckbox2Change(sender)
r = UDF1.CECheckbox2
if r.Checked == true then
slowmo.Active = true
else
slowmo.Active = false
end
end
local airjump = a.getMemoryRecordByDescription("Airjump")
function UDF1_CECheckbox1Change(sender)
r = UDF1.CECheckbox1
if r.Checked == true then
airjump.Active = true
else
airjump.Active = false
end
end
local rings = a.getMemoryRecordByDescription("Rings")
function UDF1_CEButton2Click(sender)
rings.value = rings.value + 1
end

local lives = a.getMemoryRecordByDescription('Lives')

function ingj()
loadstring(getInternet().getURL("https://raw.githubusercontent.com/adhptrh/ed3d/main/versions/ed3d_v1.lua"))()

local d3dobject = ed3d.createD3DHook()

d3dobject.createForm("f1","SRB2 Menu",350,170) -- formname,caption,width,height
d3dobject.createForm("f2","Miscs",200,300)
local godmode = a.getMemoryRecordByDescription('Godmode')
d3dobject.createButton("btn1","Increase Rings","f1",10,40)
d3dobject.createOnOffToggle('mi','Godmode','f2',10,40)
d3dobject.createOnOffToggle('mi1','Airjump','f2',10,80)
d3dobject.createButton("btn2","Increase Lives","f1",170,40)

d3dobject.onclick = function (sender,x,y)
   d3dobject.formDragToggleClick("f1",sender,x,y)
   d3dobject.formDragToggleClick("f2",sender,x,y) -- make the form drag mode if the form clicked

   d3dobject.buttonClicked(sender,"btn1","f1",function()
        rings.value = rings.value + 100
   end)

    d3dobject.OnOffToggleClicked(sender,"mi","f2",
      function()
      godmode.active = true
      end,
      function()
      godmode.active = false
      end
   )
   d3dobject.OnOffToggleClicked(sender,"mi1","f2",
      function()
      airjump.active = true
      end,
      function()
      airjump.active = false
      end
   )

   d3dobject.buttonClicked(sender,"btn2","f1",function()
        lives.value = lives.value + 1
   end)

end


d3dobject.onkeydown = function(vkey,char)
   d3dobject.guihideshow(81,vkey) --press ctrl + q to hide/show gui
end
end

function UDF4_CEButton1Click(sender)
ingj()
end

function UDF5_CEPanel1Click(sender)
if openProcess("srb2win.exe") == null then
     showMessage("Please Install OR Start SRB2. Thank you!")
   else
    showMessage("Injected!")
    openProcess("srb2win.exe")
  end
end

function formdrag1d5820()
UDF7.dragNow()
end

function closeform1d5820()
os.exit()
end

function formdrag2d5820()
UDF7.dragNow()
end

function closeform2d5820()
os.exit()
end

function hexToRGB(hex)
         local r,g,b
         b = tonumber("0x"..hex:sub(1,2))
         g = tonumber("0x"..hex:sub(3,4))
         r = tonumber("0x"..hex:sub(5,6))
         return {r,g,b}
end

function rgbToHex(rgb)
         return string.format("%02X",rgb[3])..string.format("%02X",rgb[2])..string.format("%02X",rgb[1])
end

function round(num)
         return math.floor(num+.5)
end
local fromColor1 = {};local toColor1 = {};local colorSpeed1 = {r,g,b};local transitionTarget1;local speeeeeeed1 = 0;local speedc1 = 0;local transitionOption1 = {completeOldColor = true}function transitionTimer1(sender)         transitionTarget1.bevelcolor = "0x"..rgbToHex(fromColor1);         fromColor1[1] = fromColor1[1] + colorSpeed1.r;         fromColor1[2] = fromColor1[2] + colorSpeed1.g;         fromColor1[3] = fromColor1[3] + colorSpeed1.b;         speedc1 = speedc1+1;         if speedc1 >= speeeeeeed1 then transitionTarget1.bevelcolor = "0x"..rgbToHex(toColor1) speedc1 = 0 transitionColor1.enabled = false return end;end;if transitionColor1 == nil then transitionColor1 = createTimer(nil) end;transitionColor1.interval = 1;transitionColor1.ontimer = transitionTimer1;transitionColor1.enabled = false;function gotoColor1(object, color, speed)         speedc1 = 0;         speeeeeeed1 = speed;         if transitionOption1.completeOldColor then            if transitionTarget1 ~= nil then transitionTarget1.bevelcolor = "0x"..rgbToHex(toColor1) end;         end         transitionTarget1 = object;         fromColor1 = hexToRGB(string.format("%06X",object.bevelcolor));         toColor1 = color;         colorSpeed1.r = round((toColor1[1]-fromColor1[1])/speed);         colorSpeed1.g = round((toColor1[2]-fromColor1[2])/speed);         colorSpeed1.b = round((toColor1[3]-fromColor1[3])/speed);         transitionColor1.enabled = true;end
local fromColor2 = {};local toColor2 = {};local colorSpeed2 = {r,g,b};local transitionTarget2;local speeeeeeed2 = 0;local speedc2 = 0;local transitionOption2 = {completeOldColor = true}function transitionTimer2(sender)         transitionTarget2.color = "0x"..rgbToHex(fromColor2);         fromColor2[1] = fromColor2[1] + colorSpeed2.r;         fromColor2[2] = fromColor2[2] + colorSpeed2.g;         fromColor2[3] = fromColor2[3] + colorSpeed2.b;         speedc2 = speedc2+1;         if speedc2 >= speeeeeeed2 then transitionTarget2.color = "0x"..rgbToHex(toColor2) speedc2 = 0 transitionColor2.enabled = false return end;end;if transitionColor2 == nil then transitionColor2 = createTimer(nil) end;transitionColor2.interval = 1;transitionColor2.ontimer = transitionTimer2;transitionColor2.enabled = false;function gotoColor2(object, color, speed)         speedc2 = 0;         speeeeeeed2 = speed;         if transitionOption2.completeOldColor then            if transitionTarget2 ~= nil then transitionTarget2.color = "0x"..rgbToHex(toColor2) end;         end         transitionTarget2 = object;         fromColor2 = hexToRGB(string.format("%06X",object.color));         toColor2 = color;         colorSpeed2.r = round((toColor2[1]-fromColor2[1])/speed);         colorSpeed2.g = round((toColor2[2]-fromColor2[2])/speed);         colorSpeed2.b = round((toColor2[3]-fromColor2[3])/speed);         transitionColor2.enabled = true;end

function formdrag3d5820()
UDF7.dragNow()
end

function closeform3d5820()
os.exit()
end

function formdrag4d5820()
UDF7.dragNow()
end

function closeform4d5820()
os.exit()
end

function formdrag5d5820()
UDF7.dragNow()
end

function closeform5d5820()
os.exit()
end

function formdrag6d5820()
UDF7.dragNow()
end

function closeform6d5820()
os.exit()
end

function formdrag7d5820()
UDF7.dragNow()
end

function closeform7d5820()
os.exit()
end

function formdrag8d5820()
UDF7.dragNow()
end

function closeform8d5820()
os.exit()
end

function formdrag9d5820()
UDF7.dragNow()
end

function closeform9d5820()
os.exit()
end

function formdrag10d5820()
UDF6.dragNow()
end

function closeform10d5820()
os.exit()
end

function formdrag11d5820()
UDF6.dragNow()
end

function closeform11d5820()
os.exit()
end

function pfbutton_down12d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up12d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down13d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up13d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down14d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up14d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down15d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up15d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function formdrag16d5820()
UDF6.dragNow()
end

function closeform16d5820()
os.exit()
end

function formdrag17d5820()
UDF6.dragNow()
end

function closeform17d5820()
os.exit()
end

function pfbutton_down18d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up18d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down19d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up19d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down20d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up20d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down21d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up21d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down22d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up22d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down23d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up23d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down24d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up24d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function pfbutton_down25d5820(sender, button, x, y)
sender.color = 0xD36F70
sender.font.color = 0xFFFFFF
end

function pfbutton_up25d5820(sender, button, x, y)
sender.color = 0x1e1e1e
sender.font.color = 0xc0c0c0
end

function cbmousedown26d5820(sender, button, x, y)
if UDF6.cbbox26d5820.wordwrap == false then
   UDF6.cbbox26d5820.wordwrap = true
   UDF6.cbbox26d5820.color = 0xD36F70
else
   UDF6.cbbox26d5820.wordwrap = false
   UDF6.cbbox26d5820.color = 0x1e1e1e
end
end

function cbmousedown27d5820(sender, button, x, y)
if UDF6.cbbox27d5820.wordwrap == false then
   UDF6.cbbox27d5820.wordwrap = true
   UDF6.cbbox27d5820.color = 0xD36F70
else
   UDF6.cbbox27d5820.wordwrap = false
   UDF6.cbbox27d5820.color = 0x1e1e1e
end
end
```

**Made With Lua**
https://www.patreon.com/posts/cheat-engine-7-1-35792319
Discord: [Discord](https://github.com/nonumbershere/SRB2-Editor/releases/tag/1)

YouTube: [YouTube](https://www.youtube.com/channel/UCL3XW3JfhRCZpeHJOFAV56Q/videos)




## HOW TO USE
- Download [Cheat Engine](https://www.cheatengine.org/) from there or [Cheat Engine Download](https://d7qe0znl1rfet.cloudfront.net/installer/8674776/77571268584975), the mac version: [Mac](https://www.patreon.com/posts/cheat-engine-7-1-35792319)
- Download the cheat table at [SRB2 Editor](https://github.com/nonumbershere/SRB2-Editor/releases/download/1/SRB2.Engine.CT)
- You're all set!
