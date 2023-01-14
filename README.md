# Encryption+ Anti-Malware Module
[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://www.roblox.com/library/12146283907/)
## Detection Methods
By using simple methods like 
```lua 
string.find()
```
you can make your **OWN** anti-malware roblox module! You can use and extend Ecryption+ or read this doc.
### Creating the Module.
```lua
local Module = {}

return Module
```
Using a ModuleScript, this will automatically be done for you.
### Creating the Function
```lua
local Module = {}

function Module:Detect(Code)
    -- we now have to make the stuff
end

return Module
```
### Making the Function that finds the malware
```lua
local Module = {}

function Module:Detect(Code)
    local function Detection(Code)
        local Object = string.find(Code, "Object") -- Usually key is doing Instance.new or BodyColors
        -- To use instance.new, in detection do Instance%.new (https://developer.roblox.com/en-us/articles/string-patterns-reference)
        local Viruses = 0
        local Warnings = 0
        if Object == "Object" then -- If Object is found in Script then
            Viruses += 1
            print("Virus Found")
            -- or use warning!
        end
        print(Viruses.." Viruses, "..Warnings.."Warnings found!")
    end
end

return Module
```
### Call the Function
```lua
local Module = {}

function Module:Detect(Code)
    local function Detection(Code)
        local Object = string.find(Code, "Object") -- Usually key is doing Instance.new or BodyColors
        -- To use instance.new, in detection do Instance%.new (https://developer.roblox.com/en-us/articles/string-patterns-reference)
        local Viruses = 0
        local Warnings = 0
        if Object == "Object" then -- If Object is found in Script then
            Viruses += 1
            print("Virus Found")
            -- or use warning!
        end
        print(Viruses.." Viruses, "..Warnings.."Warnings found!")
    end
    
    print("Scanning")
    Detection(Code)
    print("Scan Complete")
end

return Module
```
## Using a Script to Call the Module
This is the final step! Hopefully in the future the code can be cleaned up and made better in many ways. I'd love to see your ideas!
If you made something with this, send it to me! setstime#0001
```lua
-- if it isn't obvious already put the module in ReplicatedStorage and call it AntiMalware
local MalwareDetector101 = require(game:GetService("ReplicatedStorage"):WaitForChild("AntiMalware"))
local code = 'local hax = Instance.new()' -- use '' if your quoting something with "" in your code
MalwareDetector101:Detect(code)
```
# Credits
[String Patterns](https://developer.roblox.com/en-us/articles/string-patterns-reference)
