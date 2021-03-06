## Anycomplete

The magic of Google Autocomplete while you're typing. Anywhere.

![](http://i.imgur.com/kYoE7hs.gif)

### Installation

An extension for [Hammerspoon](http://hammerspoon.org/). Once Hammerspoon is installed, copy `anycomplete.lua` to `~/.hammerspoon/`.
To initialize, add `dofile("anycomplete.lua")` to `~/.hammerspoon/init.lua` (creating it if it does not exist). Reload the Hammerspoon config.

### Usage

Trigger with the hotkey ⌃⌥⌘G. Once you start typing, suggestions will populate.
They can be choosen with ⌘1-9 or by pressing the arrow keys and Enter.

The hotkey can be changed by editing [hs.hotkey.bind](https://github.com/nathancahill/hammerspoon-config/blob/master/anycomplete.lua#L5).

### Privacy

No keystrokes are sent to Google until you trigger the hotkey and start typing. If you prefer DuckDuckGo, replace `GOOGLE_ENDPOINT` with:
`'https://duckduckgo.com/ac/?q=%s'` and the `imap` function with this:

```
choices = hs.fnutils.imap(results[2], function(result)
    return {
        ["text"] = result["phrase"],
    }
end)
```
