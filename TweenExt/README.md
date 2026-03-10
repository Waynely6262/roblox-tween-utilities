# Tween Extensions

## TweenCallback

TweenCallback enables binding of a callback function to handle a tween. For example, Roblox's TweenService does not support tweening the Scale of a Model. By using TweenCallback, a callback function can be set as:
```luau
local TweenCallback = require(game.ReplicatedStorage.Modules.Utility.TweenCallback)
local Model = Instance.new("Model")
local callback = function(a: number)
  Model:ScaleTo(a)
end

local onComplete = function()
  Model:Destroy()
end

TweenCallback.run(<duration>, <easing function or nil>, callback, onComplete)
```

## Tween

This module was initially created to perform TweenService operations with less syntax. This module specifically avoids:
- Creating TweenInfo objects
- Creating Tween.Completed connections to handle the finish of a Tween
  
Although it is noted that these upsides may introduce downsides in terms of back-end optimizations made by TweenService, it creates clearer, more readable syntax in scenarios where performance is negligible, or for scenarios where the program is written as part of a showcase.
