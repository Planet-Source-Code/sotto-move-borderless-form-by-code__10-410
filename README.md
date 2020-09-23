<div align="center">

## Move borderless form by code


</div>

### Description

Move your form by clicking a control (or just the form) and moving mouse. No timercontrol used.
 
### More Info
 
add a command button named cmdTest on the form

add this code

test it :-)

if you want it to work with the form (click form - drag) you just need to change the sub-names and the Handles things to

private sub formname_mousedown(...) handles mybase.mousedown

(do this also with the mousemove event)


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[SoTTo](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/sotto.md)
**Level**          |Beginner
**User Rating**    |4.6 (23 globes from 5 users)
**Compatibility**  |VB\.NET
**Category**       |[Controls/ Forms/ Dialogs/ Menus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/controls-forms-dialogs-menus__10-3.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/sotto-move-borderless-form-by-code__10-410/archive/master.zip)

### API Declarations

```
I got this code from a forum on vbcity.com
changed it to get it to work with every control (not only the form itself)
```


### Source Code

```
Private mouse_offset As Point
 Private Sub cmdTest_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles cmdTest.MouseDown
  mouse_offset = New Point(-e.X, -e.Y)
 End Sub
 Private Sub cmdTest_MouseMove(ByVal Sender As System.Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles cmdTest.MouseMove
  If e.Button = MouseButtons.Left Then
   Dim mousePos As Point = Sender.findform().MousePosition
   mousePos.Offset(mouse_offset.X, mouse_offset.Y)
   Sender.findform().Location = mousePos
  End If
 End Sub
```

