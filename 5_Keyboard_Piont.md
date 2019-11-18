# Change comma to Point on German keyboard

On German keyboards is the Point on the Numpad a comma. It ist easier to have a point on the Numpad.

```
xmodmap -pke > .Xmodmap
sudo nano .Xmodmap
```

old key is a comma
```
keycode 91 = KP_Delete KP_Separator KP_Delete KP_Separator
```

change comma -> point
```
keycode 91 = KP_Delete period KP_Delete period
```
