    local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/naypramx/Ui__Project/Script/XeNonUi", true))()
    library:CreateWatermark("Sleep Hub") -- Config แตกนะเดียวค่อยแก้รอเน็ตมาก่อน By MeowX#0001
    local CenterHubNo1 = library:CreateWindow("Sleep Hub | Master Pirate",Enum.KeyCode.RightControl)
    local Tab = CenterHubNo1:CreateTab("Main")
    local AutoFarm = Tab:CreateSector("AutoFarm","left")
    AutoFarm:AddButton("QuestLv.0",function()
        local args = {
            [1] = workspace.NPC:FindFirstChild("Quest [Lv.0+]"),
            [2] = workspace.NPC:FindFirstChild("Quest [Lv.0+]"),
            [3] = workspace.NPC:FindFirstChild("Quest [Lv.0+]")
        }
        
        game:GetService("ReplicatedStorage").Assets.Remote.RemoteFunction.Talking:InvokeServer(unpack(args))
    end)
    AutoFarm:AddButton("QuestLv.10",function()
            local args = {
                [1] = workspace.NPC:FindFirstChild("Quest [Lv.10+]"),
                [2] = workspace.NPC:FindFirstChild("Quest [Lv.10+]"),
                [3] = workspace.NPC:FindFirstChild("Quest [Lv.10+]")
            }
            
            game:GetService("ReplicatedStorage").Assets.Remote.RemoteFunction.Talking:InvokeServer(unpack(args))
    end)
    
    
    function Stats(Stats)
    local args = {
        [1] = Stats,
        [2] = Point
    }
    
    game:GetService("ReplicatedStorage").Assets.Remote.RemoteEvent.Stats:FireServer(unpack(args))
    end
    
    local AutoFarm = Tab:CreateSector("Stats","right")
    AutoFarm:AddToggle("Strength",false,function(t)
       _G.Strength = t
        while _G.Strength do wait()
        pcall(function()
        Stats("Strength")
    end)
    end
    end)
    AutoFarm:AddToggle("Defense",false,function(t)
       _G.Defense = t
        while _G.Defense do wait()
        pcall(function()
        Stats("Defense")
    end)
    end
    end)
    AutoFarm:AddToggle("Sword",false,function(t)
       _G.Sword = t
        while _G.Sword do wait()
           pcall(function()
               Stats("Sword")
           end)
        end
    end)
    AutoFarm:AddToggle("DevilFruit",false,function(t)
       _G.DevilFruit = t
       while _G.DevilFruit do wait()
           pcall(function()
               Stats("DevilFruit")
           end)
        end
    end)
    AutoFarm:AddSlider("Point",1,1,100,1,function(x)
        Point = x
    end)
    
