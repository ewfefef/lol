local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Window = OrionLib:MakeWindow({Name = "Bedwars| Owner", HidePremium = false, IntroText = "Private Hack" , SaveConfig = true, ConfigFolder = "Bedwars"})


local MainTab = Window:MakeTab({
	Name = "Main Private",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

MainTab:AddToggle({
	Name = "Killaura!",
	Default = false,
	Callback = function(Value)
		print(Value)
 

	end    
})


MainTab:AddToggle({
	Name = "Reach!",
	Default = false,
	Callback = function(Value)
		print(Value)
	end    
})


MainTab:AddToggle({
	Name = "NoFall",
	Default = false,
	Callback = function(Value)
		print(Value)

	end
})

MainTab:AddToggle({
	Name = "speed",
	Default = false,
	Callback = function(Value)
		print(Value)
	end    
})

MainTab:AddSlider({
	Name = "AddSlider",
	Min = 16,
	Max = 30,
	Default = 20,
	Color = Color3.fromRGB(255,255,255),
	Increment = 1,
	ValueName = "Speed",
	Callback = function(Value)
		print(Value)
	end    
})

OrionLib:MakeNotification({
	Name = "Our Discord!",
	Content = "Notification content... join for future updates https://discord.gg/C8j6xP8ftz",
	Image = "rbxassetid://4483345998",
	Time = 10
})


