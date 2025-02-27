local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()


local Window = Rayfield:CreateWindow({
   Name = "UraniumShade/GUI/PRIVÉ",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "UraniumShade/GUI/PRIVÉ",
   LoadingSubtitle = "GUI",
   Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "Big Hub"
   },

   Discord = {
      Enabled = false, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "noinvitelink", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

   KeySystem = false, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
   }
})


local PLAYERTab = Window:CreateTab("PLAYER", 4483362458) -- Title, Image


local Section = PLAYERTab:CreateSection("Anti Afk")


local Button = PLAYERTab:CreateButton({
   Name = "Anti Afk (PC)",
   Callback = function()
   loadstring(game:HttpGet(('https://raw.githubusercontent.com/RTrade/Voidz/main/AntiAFK.lua'),true))()
   -- The function that takes place when the button is pressed
   end,
})


local Button = PLAYERTab:CreateButton({
   Name = "Anti Afk (MOBILE)",
   Callback = function()
   loadstring(game:HttpGet(('https://raw.githubusercontent.com/Proxylol/OtherScripts/main/AntiAfk.lua'),true))()
   -- The function that takes place when the button is pressed
   end,
})


local EXPTab = Window:CreateTab("EXP", 4483362458) -- Title, Image


local Section = EXPTab:CreateSection("Auto Coin")


local isHitting = false
 local Toggle = EXPTab:CreateToggle({
    Name = "Auto Coin",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        isHitting = Value

        if isHitting then
            -- Lancer une boucle non bloquante
            task.spawn(function()
                while isHitting do
game:GetService("ReplicatedStorage"):WaitForChild("Events"):WaitForChild("CoinEvent"):FireServer()
task.wait(0.1) -- Pause
wait()
end
end)
        end
    -- The function that takes place when the toggle is pressed
    -- The variable (Value) is a boolean on whether the toggle is true or false
    end,
 })
 
 
local Section = EXPTab:CreateSection("Farm Dummy Spawn")
 
 
 local isHitting = false
local Toggle = EXPTab:CreateToggle({
   Name = "Farm Dummy Spawn",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   local player = game.Players.LocalPlayer
    local character = player.Character or player.CharacterAdded:Wait()
    
    local function teleportToTarget(targetPosition)
        if character and character:FindFirstChild("HumanoidRootPart") then
            character.HumanoidRootPart.CFrame = CFrame.new(targetPosition)
        end
    end
    
    local function teleportToDummy()
        local dummy = workspace.MAP.dummies.Dummy
        if dummy and dummy:FindFirstChild("HumanoidRootPart") then
            local dummyPosition = dummy.HumanoidRootPart.Position
            teleportToTarget(dummyPosition + Vector3.new(0, 5, 0,3))
        end
    end
    
    -- Exemple d'utilisation : téléporte le joueur vers le Dummy
    teleportToDummy()
    local args = {
        [1] = workspace.MAP.dummies.Dummy.Humanoid,
        [2] = 2
    }
    
     isHitting = Value
    
            if isHitting then
                -- Lancer une boucle non bloquante
                task.spawn(function()
                    while isHitting do
    
    game:GetService("ReplicatedStorage").jdskhfsIIIllliiIIIdchgdIiIIIlIlIli:FireServer(unpack(args))
    task.wait(0.1) -- Pause
    end
                end)
            end
   -- The function that takes place when the toggle is pressed
   -- The variable (Value) is a boolean on whether the toggle is true or false
   end,
})


local isHitting = false
local Toggle = EXPTab:CreateToggle({
   Name = "Firball Dummy Spawn",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   local args = {
                [1] = Vector3.new(-126.39784240722656, 645.3551025390625, 594.0857543945312),
                [2] = "NewFireball"
            }
            
             isHitting = Value
            
                    if isHitting then
                        -- Lancer une boucle non bloquante
                        task.spawn(function()
                            while isHitting do
            
            game:GetService("ReplicatedStorage").SkillsInRS.RemoteEvent:FireServer(unpack(args))
            task.wait(0.1) -- Pause
            end
                        end)
                    end
                    local args = {
    [1] = Vector3.new(-80.19454193115234, 595.6495361328125, 813.2150268554688),
    [2] = "NewLightningball"
}

 isHitting = Value

        if isHitting then
            -- Lancer une boucle non bloquante
            task.spawn(function()
                while isHitting do

game:GetService("ReplicatedStorage").SkillsInRS.RemoteEvent:FireServer(unpack(args))
task.wait(0.1) -- Pause
end
            end)
        end
   -- The function that takes place when the toggle is pressed
   -- The variable (Value) is a boolean on whether the toggle is true or false
   end,
})


local Section = EXPTab:CreateSection("Farm 5K")


local isHitting = false
local Toggle = EXPTab:CreateToggle({
   Name = "Farm Dummy Spawn",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-81.58647155761719, 594.46826171875, 814.044189453125)
local args = {
    [1] = workspace.MAP:FindFirstChild("5k_dummies").Dummy2.Humanoid,
    [2] = 4
}

 isHitting = Value

        if isHitting then
            -- Lancer une boucle non bloquante
            task.spawn(function()
                while isHitting do

game:GetService("ReplicatedStorage").jdskhfsIIIllliiIIIdchgdIiIIIlIlIli:FireServer(unpack(args))
task.wait(0.1) -- Pause
end
            end)
        end
   -- The function that takes place when the toggle is pressed
   -- The variable (Value) is a boolean on whether the toggle is true or false
   end,
})


local isHitting = false
local Toggle = EXPTab:CreateToggle({
   Name = "Firball Dummy Spawn",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   local args = {
            [1] = Vector3.new(-83.04418182373047, 595.0643920898438, 813.4301147460938),
            [2] = "NewFireball"
        }
        
         isHitting = Value
        
                if isHitting then
                    -- Lancer une boucle non bloquante
                    task.spawn(function()
                        while isHitting do
        
        game:GetService("ReplicatedStorage").SkillsInRS.RemoteEvent:FireServer(unpack(args))
        task.wait(0.1) -- Pause
        end
                    end)
                end
                local args = {
    [1] = Vector3.new(-126.91341400146484, 646.3195190429688, 594.6644287109375),
    [2] = "NewLightningball"
}

 isHitting = Value

        if isHitting then
            -- Lancer une boucle non bloquante
            task.spawn(function()
                while isHitting do

game:GetService("ReplicatedStorage").SkillsInRS.RemoteEvent:FireServer(unpack(args))
task.wait(0.1) -- Pause
end
            end)
        end
   -- The function that takes place when the toggle is pressed
   -- The variable (Value) is a boolean on whether the toggle is true or false
   end,
})


local NPCSTab = Window:CreateTab("NPCS", 4483362458) -- Title, Image


local Section = NPCSTab:CreateSection("NPCS")


local isHitting = false
local Toggle = NPCSTab:CreateToggle({
   Name = "Kill All Bosses",
   CurrentValue = false,
   Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   while true do
            local args = {
                [1] = workspace:WaitForChild("NPC"):WaitForChild("Griffin"):WaitForChild("Humanoid"),
                [2] = 3
            }
             
            game:GetService("ReplicatedStorage"):WaitForChild("jdskhfsIIIllliiIIIdchgdIiIIIlIlIli"):FireServer(unpack(args))
            local args = {
                [1] = workspace:WaitForChild("NPC"):WaitForChild("CRABBOSS"):WaitForChild("Humanoid"),
                [2] = 1
            }
             
            game:GetService("ReplicatedStorage"):WaitForChild("jdskhfsIIIllliiIIIdchgdIiIIIlIlIli"):FireServer(unpack(args))
            local args = {
                [1] = workspace:WaitForChild("NPC"):WaitForChild("LavaGorilla"):WaitForChild("Humanoid"),
                [2] = 5
            }
             
            game:GetService("ReplicatedStorage"):WaitForChild("jdskhfsIIIllliiIIIdchgdIiIIIlIlIli"):FireServer(unpack(args))
            local args = {
                [1] = workspace:WaitForChild("NPC"):WaitForChild("CENTAUR"):WaitForChild("Humanoid"),
                [2] = 4
            }
             
            game:GetService("ReplicatedStorage"):WaitForChild("jdskhfsIIIllliiIIIdchgdIiIIIlIlIli"):FireServer(unpack(args))
            local args = {
                [1] = workspace:WaitForChild("NPC"):WaitForChild("DragonGiraffe"):WaitForChild("Humanoid"),
                [2] = 1
            }
             
            game:GetService("ReplicatedStorage"):WaitForChild("jdskhfsIIIllliiIIIdchgdIiIIIlIlIli"):FireServer(unpack(args))
            wait()
            end
   -- The function that takes place when the toggle is pressed
   -- The variable (Value) is a boolean on whether the toggle is true or false
   end,
})
