# rblx-backpack
The Roblox core backpack, minus CoreGui dependencies.
The code is contained with the module `Backpack.Lua`. All three files are Roblox core scripts
extracted from the Roblox folder, with some modification.

## Example usage
```lua
local StarterGui = game:GetService("StarterGui")
local backpack = require(path.to.backpack)

-- Disable the built-in backpack
StarterGui:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, false)
local newBackpack = require(backpack)
newBackpack.SlotsChanged.Event:Connect(function()
    print("SlotsChanged!", newBackpack:GetSlots())
end)
```


## Modifications

1. Slots can now be accessed by running BackpackScript:GetSlots()
2. BackpackScript.SlotsChanged is a bindable event which is fired when tool order is updated. It is not passed any parameters. 
3. The backpack is no longer VR compatible. If VR is enabled, the normal UI should be used.
4. The interface will not enlarge for "massive" screens. This feature depended on APIs which not available to normal scripts.


## License
See License.txt
