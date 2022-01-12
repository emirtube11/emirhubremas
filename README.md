local Material = loadstring(game:HttpGet("https://raw.githubusercontent.com/Kinlei/MaterialLua/master/Module.lua"))()

local X = Material.Load({
	Title = "EmirHUB (Remastered)",
	Style = 1,
	SizeX = 500,
	SizeY = 350,
	Theme = "Dark",
	ColorOverrides = {
		MainFrame = Color3.fromRGB(0,0,0)
	}
})


local Y = X.New({
	Title = "Player"
})

local H = X.New({
	Title = "Music Hub V2"
})

local Z = X.New({
	Title = "Prison Life"
})

local T = X.New({
	Title = "Ninja Legends"
})

--MusicHubV2

local A = H.Button({
	Text = "Skids Hub",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/DarkManee/Skids-Hub-V2/main/V2"))();
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Execute Skids Hub."
			})
		end
	}
})

local A = H.Button({
	Text = "Logger",
	Callback = function()
		loadstring(game:HttpGet(('https://raw.githubusercontent.com/emirtube11/logger/main/README.md'),true))()
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Execute Skids Hub."
			})
		end
	}
})

--Player

local A = Y.Button({
	Text = "Emir Hub V2",
	Callback = function()
		loadstring(game:HttpGet("https://raw.githubusercontent.com/emirtube11/EmirHUBV2/main/README.md"))();
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Execute EmirHUB V2"
			})
		end
	}
})


local C = Y.Slider({
	Text = "Walk Speed",
	Callback = function(Value)
		game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
	end,
	Min = 16,
	Max = 400,
	Def = 16
})
local C = Y.Slider({
	Text = "Jump Power",
	Callback = function(Value)
		game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
	end,
	Min = 50,
	Max = 400,
	Def = 50
})

--Prison Life

local A = Z.Button({
	Text = "Get All Guns",
	Callback = function()
		workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["Remington 870"].ITEMPICKUP)
				workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["M4A1"].ITEMPICKUP)
				workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["AK-47"].ITEMPICKUP)
				workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.giver["M9"].ITEMPICKUP)
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Get All Guns (Note: You Need Wait Some Second For Get All Guns)"
			})
		end
	}
})

local A = Z.Button({
	Text = "Open Prison Gate",
	Callback = function()
		workspace.Remote.ItemHandler:InvokeServer(workspace.Prison_ITEMS.buttons["Prison Gate"]["Prison Gate"])
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Opens Prison Gate"
			})
		end
	}
})


local A = Z.Button({
	Text = "Be Police",
	Callback = function()
			workspace.Remote.TeamEvent:FireServer("Bright blue")
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Become Police"
			})
		end
	}
})

local A = Z.Button({
	Text = "Be Inmate",
	Callback = function()
			workspace.Remote.TeamEvent:FireServer("Bright orange")
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Become Inmate"
			})
		end
	}
})

--Ninja Legends

local B = T.Toggle({
	Text = "Auto Swing",
	Callback = function(v)
getgenv().autoswing = v


while true do
if not getgenv().autoswing then return end
for _,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do
      if v:FindFirstChild("ninjitsuGain") then
            game.Players.LocalPlayer.Character.Humanoid:EquipTool(v)
            break
      end
end
local A_1 = "swingKatana"
local Event = game:GetService("Players").LocalPlayer.ninjaEvent
Event:FireServer(A_1)
wait(0.1)
	end
end,
	Enabled = false
})

local A = T.Button({
	Text = "Unlock All Islands",
	Callback = function()
local oldcframe = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
		for _,v in pairs(game:GetService("Workspace").islandUnlockParts:GetChildren()) do
                     game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
wait(0.2)
end
wait(0.1)
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = oldcframe
	end,
	Menu = {
		Information = function(self)
			X.Banner({
				Text = "Unlock All Islands!, You Need Wait Some Second."
			})
		end
	}
})

local B = T.Toggle({
	Text = "Auto Buy All Swords",
	Callback = function(v)
		getgenv().buyswords = v
                while true do
                     if not getgenv().buyswords then return end
local A_1 = "buyAllSwords"
local A_2 = "Inner Peace Island"
local Event = game:GetService("Players").LocalPlayer.ninjaEvent
Event:FireServer(A_1)
wait(0.5)
end
	end,
	Enabled = false
})

local B = T.Toggle({
	Text = "Auto Buy All Belts",
	Callback = function(v)
		getgenv().buybelts = v
                while true do
                     if not getgenv().buybelts then return end
local A_1 = "buyAllBelts"
local A_2 = "Inner Peace Island"
local Event = game:GetService("Players").LocalPlayer.ninjaEvent
Event:FireServer(A_1)
wait(0.5)
end
	end,
	Enabled = false
})
