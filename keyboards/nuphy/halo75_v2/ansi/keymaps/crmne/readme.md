# crmne Halo75 V2 Layout

This keymap keeps the NuPhy defaults where they already feel great and fixes the spots that drove me nuts.

## Mac Layer

- Stock NuPhy macOS layout, untouched. Muscle memory stays happy.

## Windows Layer

The top row now behaves like the media/utility keys I expect on Linux + Hyprland:

| Key | Action | X11/Wayland Symbol |
| --- | --- | --- |
| `KC_ESC` | Escape, of course | `Escape` |
| `KC_BRID` | Monitor brightness down | `XF86MonBrightnessDown` |
| `KC_BRIU` | Monitor brightness up | `XF86MonBrightnessUp` |
| `KC_MISSION_CONTROL` | Drop into Hyprland overview | `XF86LaunchA` |
| `KC_WWW_SEARCH` | Desktop search launcher | `XF86Search` |
| `KC_F20` | Mic mute toggle | `XF86AudioMicMute` |
| `MAC_DND` | System Do Not Disturb | `XF86DoNotDisturb` |
| `KC_MPRV / KC_MPLY / KC_MNXT` | Media controls | `XF86Audio{Prev,Play,Next}` |
| `KC_MUTE / KC_VOLD / KC_VOLU` | Volume controls | `XF86Audio{Mute,LowerVolume,RaiseVolume}` |
| `KC_PSCR` | Take a screenshot | `PrintScreen` |

Everything past that row mirrors the stock Windows layer so the rest of the board feels familiar.

## Why it Works

- My [dotfiles](https://github.com/crmne/dotfiles) bind those XF86 codes to Hyprland actions — peek at [`dot_config/hypr/bindings.conf`](https://github.com/crmne/dotfiles/blob/master/dot_config/hypr/bindings.conf) if you want the full picture.
- The Mac and Windows layers now share the same media muscle memory, so swapping laptops is painless.
- Increased debounce in `keyboard.json` cuts the chatter I was seeing on the `n`/`h` switches.

## Build It

```sh
qmk doctor
qmk compile -kb nuphy/halo75_v2/ansi -km crmne
qmk flash   -kb nuphy/halo75_v2/ansi -km crmne
```

Hold *Esc* while plugging in USB to drop the Halo75 V2 into DFU before flashing.
