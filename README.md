# _16n

norns lib for easy integration w/ [16n](https://16n-faderbank.github.io/).

automatically retrieves a plugged 16n configuration at init (via sysex) and bind a callback to slider changes.


## example usage

```lua
_16n = include("lib/_16n")

function init()
  _16n.init(_16n_slider_callback)
end

function _16n_slider_callback(midi_msg)
  local slider_id = _16n.cc_2_slider_id(midi_msg.cc)
  local v = midi_msg.val

  print("slider #"..slider_id.." just got its value changed to "..v)
end
```
