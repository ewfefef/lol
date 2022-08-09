local Player = game:GetService("Players").LocalPlayer
local Mouse = Player:GetMouse()

local TextService = game:GetService("TextService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local InputService = game:GetService("UserInputService")
local CoreGuiService = game:GetService("CoreGui")
local ContentService = game:GetService("ContentProvider")

local Themes = {
	Light = {
		MainFrame = Color3.fromRGB(255,255,255),
		Minimise = Color3.fromRGB(255,106,0),
		MinimiseAccent = Color3.fromRGB(147,59,0),
		Maximise = Color3.fromRGB(25,255,0),
		MaximiseAccent = Color3.fromRGB(0,255,110),
		NavBar = Color3.fromRGB(124,37,255),
		NavBarAccent = Color3.fromRGB(255,255,255),
		NavBarInvert = Color3.fromRGB(30,30,30),
		TitleBar = Color3.fromRGB(124,37,255),
		TitleBarAccent = Color3.fromRGB(255,255,255),
		Overlay = Color3.fromRGB(124,37,255),
		Banner = Color3.fromRGB(255,255,255),
		BannerAccent = Color3.fromRGB(124,37,255),
		Content = Color3.fromRGB(124,37,255),
		Button = Color3.fromRGB(124,37,255),
		ButtonAccent = Color3.fromRGB(255,255,255),
		ChipSet = Color3.fromRGB(124,37,255),
		ChipSetAccent = Color3.fromRGB(255,255,255),
		DataTable = Color3.fromRGB(124,37,255),
		DataTableAccent = Color3.fromRGB(255,255,255),
		Slider = Color3.fromRGB(255,255,255),
		SliderAccent = Color3.fromRGB(124,37,255),
		Toggle = Color3.fromRGB(124,37,255),
		ToggleAccent = Color3.fromRGB(255,255,255),
		Dropdown = Color3.fromRGB(255,255,255),
		DropdownAccent = Color3.fromRGB(124,37,255),
		ColorPicker = Color3.fromRGB(255,255,255),
		ColorPickerAccent = Color3.fromRGB(124,37,255),
		TextField = Color3.fromRGB(124,37,255),
		TextFieldAccent = Color3.fromRGB(124,37,255),
	},
	Dark = {
		MainFrame = Color3.fromRGB(30,30,30),
		Minimise = Color3.fromRGB(255,106,0),
		MinimiseAccent = Color3.fromRGB(147,59,0),
		Maximise = Color3.fromRGB(25,255,0),
		MaximiseAccent = Color3.fromRGB(0,255,110),
		NavBar = Color3.fromRGB(55,55,55),
		NavBarAccent = Color3.fromRGB(255,255,255),
		NavBarInvert = Color3.fromRGB(235,235,235),
		TitleBar = Color3.fromRGB(55,55,55),
		TitleBarAccent = Color3.fromRGB(255,255,255),
		Overlay = Color3.fromRGB(175,175,175),
		Banner = Color3.fromRGB(55,55,55),
		BannerAccent = Color3.fromRGB(255,255,255),
		Content = Color3.fromRGB(85,85,85),
		Button = Color3.fromRGB(85,85,85),
		ButtonAccent = Color3.fromRGB(255,255,255),
		ChipSet = Color3.fromRGB(235,235,235),
		ChipSetAccent = Color3.fromRGB(85,85,85),
		DataTable = Color3.fromRGB(235,235,235),
		DataTableAccent = Color3.fromRGB(85,85,85),
		Slider = Color3.fromRGB(85,85,85),
		SliderAccent = Color3.fromRGB(235,235,235),
		Toggle = Color3.fromRGB(205,205,205),
		ToggleAccent = Color3.fromRGB(125,125,125),
		Dropdown = Color3.fromRGB(85,85,85),
		DropdownAccent = Color3.fromRGB(235,235,235),
		ColorPicker = Color3.fromRGB(85,85,85),
		ColorPickerAccent = Color3.fromRGB(235,235,235),
		TextField = Color3.fromRGB(175,175,175),
		TextFieldAccent = Color3.fromRGB(255,255,255),
	},
	Mocha = {
		MainFrame = Color3.fromRGB(255,255,255),
		Minimise = Color3.fromRGB(219, 210, 202),
		MinimiseAccent = Color3.fromRGB(219, 210, 202),
		Maximise = Color3.fromRGB(189, 183, 177),
		MaximiseAccent = Color3.fromRGB(189, 183, 177),
		NavBar = Color3.fromRGB(176, 148, 125),
		NavBarAccent = Color3.fromRGB(255,255,255),
		NavBarInvert = Color3.fromRGB(30,30,30),
		TitleBar = Color3.fromRGB(176, 148, 125),
		TitleBarAccent = Color3.fromRGB(255,255,255),
		Overlay = Color3.fromRGB(176, 148, 125),
		Banner = Color3.fromRGB(255,255,255),
		BannerAccent = Color3.fromRGB(176, 148, 125),
		Content = Color3.fromRGB(176, 148, 125),
		Button = Color3.fromRGB(176, 148, 125),
		ButtonAccent = Color3.fromRGB(255,255,255),
		ChipSet = Color3.fromRGB(176, 148, 125),
		ChipSetAccent = Color3.fromRGB(255,255,255),
		DataTable = Color3.fromRGB(176, 148, 125),
		DataTableAccent = Color3.fromRGB(255,255,255),
		Slider = Color3.fromRGB(255,255,255),
		SliderAccent = Color3.fromRGB(176, 148, 125),
		Toggle = Color3.fromRGB(176, 148, 125),
		ToggleAccent = Color3.fromRGB(255,255,255),
		Dropdown = Color3.fromRGB(255,255,255),
		DropdownAccent = Color3.fromRGB(176, 148, 125),
		ColorPicker = Color3.fromRGB(255,255,255),
		ColorPickerAccent = Color3.fromRGB(176, 148, 125),
		TextField = Color3.fromRGB(175,175,175),
		TextFieldAccent = Color3.fromRGB(255,255,255)
	},
	Aqua = {
		MainFrame = Color3.fromRGB(85, 255, 255),
		Minimise = Color3.fromRGB(219, 210, 202),
		MinimiseAccent = Color3.fromRGB(219, 210, 202),
		Maximise = Color3.fromRGB(189, 183, 177),
		MaximiseAccent = Color3.fromRGB(189, 183, 177),
		NavBar = Color3.fromRGB(116, 112, 140),
		NavBarAccent = Color3.fromRGB(85, 255, 255),
		NavBarInvert = Color3.fromRGB(85, 255, 255),
		TitleBar = Color3.fromRGB(85, 255, 255),
		TitleBarAccent = Color3.fromRGB(255,255,255),
		Overlay = Color3.fromRGB(116, 112, 140),
		Banner = Color3.fromRGB(85, 255, 255),
		BannerAccent = Color3.fromRGB(116, 112, 140),
		Content = Color3.fromRGB(85, 255, 255),
		Button = Color3.fromRGB(85, 255, 255),
		ButtonAccent = Color3.fromRGB(255,255,255),
		ChipSet = Color3.fromRGB(116, 112, 140),
		ChipSetAccent = Color3.fromRGB(255,255,255),
		DataTable = Color3.fromRGB(85, 255, 255),
		DataTableAccent = Color3.fromRGB(85, 255, 255),
		Slider = Color3.fromRGB(85, 255, 255,
		SliderAccent = Color3.fromRGB(85, 255, 255),
		Toggle = Color3.fromRGB(116, 112, 140),
		ToggleAccent = Color3.fromRGB(255,255,255),
		Dropdown = Color3.fromRGB(255,255,255),
		DropdownAccent = Color3.fromRGB(116, 112, 140),
		ColorPicker = Color3.fromRGB(255,255,255),
		ColorPickerAccent = Color3.fromRGB(116, 112, 140),
		TextField = Color3.fromRGB(175,175,175),
		TextFieldAccent = Color3.fromRGB(255,255,255)
	},
	Jester = {
		MainFrame = Color3.fromRGB(85, 255, 255),
		Minimise = Color3.fromRGB(219, 210, 202),
		MinimiseAccent = Color3.fromRGB(285, 255, 255),
		Maximise = Color3.fromRGB(189, 183, 177),
		MaximiseAccent = Color3.fromRGB(189, 183, 177),
		NavBar = Color3.fromRGB(219, 68, 103),
		NavBarAccent = Color3.fromRGB(255,255,255),
		NavBarInvert = Color3.fromRGB(30,30,30),
		TitleBar = Color3.fromRGB(219, 68, 103),
		TitleBarAccent = Color3.fromRGB(255,255,255),
		Overlay = Color3.fromRGB(219, 68, 103),
		Banner = Color3.fromRGB(255,255,255),
		BannerAccent = Color3.fromRGB(219, 68, 103),
		Content = Color3.fromRGB(219, 68, 103),
		Button = Color3.fromRGB(219, 68, 103),
		ButtonAccent = Color3.fromRGB(255,255,255),
		ChipSet = Color3.fromRGB(219, 68, 103),
		ChipSetAccent = Color3.fromRGB(255,255,255),
		DataTable = Color3.fromRGB(219, 68, 103),
		DataTableAccent = Color3.fromRGB(255,255,255),
		Slider = Color3.fromRGB(255,255,255),
		SliderAccent = Color3.fromRGB(219, 68, 103),
		Toggle = Color3.fromRGB(219, 68, 103),
		ToggleAccent = Color3.fromRGB(255,255,255),
		Dropdown = Color3.fromRGB(255,255,255),
		DropdownAccent = Color3.fromRGB(219, 68, 103),
		ColorPicker = Color3.fromRGB(255,255,255),
		ColorPickerAccent = Color3.fromRGB(219, 68, 103),
		TextField = Color3.fromRGB(175,175,175),
		TextFieldAccent = Color3.fromRGB(255,255,255),
	}
}

local Types = {
	"RoundFrame",
	"Shadow",
	"Circle",
	"CircleButton",
	"Frame",
	"Label",
	"Button",
	"SmoothButton",
	"Box",
	"ScrollingFrame",
	"Menu",
	"NavBar"
}

local ActualTypes = {
	RoundFrame = "ImageLabel",
	Shadow = "ImageLabel",
	Circle = "ImageLabel",
	CircleButton = "ImageButton",
	Frame = "Frame",
	Label = "TextLabel",
	Button = "TextButton",
	SmoothButton = "ImageButton",
	Box = "TextBox",
	ScrollingFrame = "ScrollingFrame",
	Menu = "ImageButton",
	NavBar = "ImageButton"
}

local Properties = {
	RoundFrame = {
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554237731",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(3,3,297,297)
	},
	SmoothButton = {
		AutoButtonColor = false,
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554237731",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(3,3,297,297)
	},
	Shadow = {
		Name = "Shadow",
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554236805",
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(23,23,277,277),
		Size = UDim2.fromScale(1,1) + UDim2.fromOffset(30,30),
		Position = UDim2.fromOffset(-15,-15)
	},
	Circle = {
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5554831670"
	},
	CircleButton = {
		BackgroundTransparency = 1,
		AutoButtonColor = false,
		Image = "http://www.roblox.com/asset/?id=5554831670"
	},
	Frame = {
		BackgroundTransparency = 1,
		BorderSizePixel = 0,
		Size = UDim2.fromScale(1,1)
	},
	Label = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	Button = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	Box = {
		BackgroundTransparency = 1,
		Position = UDim2.fromOffset(5,0),
		Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0),
		TextSize = 14,
		TextXAlignment = Enum.TextXAlignment.Left
	},
	ScrollingFrame = {
		BackgroundTransparency = 1,
		ScrollBarThickness = 0,
		CanvasSize = UDim2.fromScale(0,0),
		Size = UDim2.fromScale(1,1)
	},
	Menu = {
		Name = "More",
		AutoButtonColor = false,
		BackgroundTransparency = 1,
		Image = "http://www.roblox.com/asset/?id=5555108481",
		Size = UDim2.fromOffset(20,20),
		Position = UDim2.fromScale(1,0.5) - UDim2.fromOffset(25,10)
	},
	NavBar = {
		Name = "SheetToggle",
		Image = "http://www.roblox.com/asset/?id=5576439039",
		BackgroundTransparency = 1,
		Size = UDim2.fromOffset(20,20),
		Position = UDim2.fromOffset(5,5),
		AutoButtonColor = false
	}
}

function FindType(String)
	for _, Type in next, Types do
		if Type:sub(1, #String):lower() == String:lower() then
			return Type
		end
	end
	return false
end

local Objects = {}

function Objects.new(Type)
	local TargetType = FindType(Type)
	if TargetType then
		local NewImage = Instance.new(ActualTypes[TargetType])
		if Properties[TargetType] then
			for Property, Value in next, Properties[TargetType] do
				NewImage[Property] = Value
			end
		end
		return NewImage
	else
		return Instance.new(Type)
	end
end

local function GetXY(GuiObject)
	local Max, May = GuiObject.AbsoluteSize.X, GuiObject.AbsoluteSize.Y
	local Px, Py = math.clamp(Mouse.X - GuiObject.AbsolutePosition.X, 0, Max), math.clamp(Mouse.Y - GuiObject.AbsolutePosition.Y, 0, May)
	return Px/Max, Py/May
end

local function CircleAnim(GuiObject, EndColour, StartColour)
	local PX, PY = GetXY(GuiObject)
	local Circle = Objects.new("Circle")
	Circle.Size = UDim2.fromScale(0,0)
	Circle.Position = UDim2.fromScale(PX,PY)
	Circle.ImageColor3 = StartColour or GuiObject.ImageColor3
	Circle.ZIndex = 200
	Circle.Parent = GuiObject
	local Size = GuiObject.AbsoluteSize.X
	TweenService:Create(Circle, TweenInfo.new(1), {Position = UDim2.fromScale(PX,PY) - UDim2.fromOffset(Size/2,Size/2), ImageTransparency = 1, ImageColor3 = EndColour, Size = UDim2.fromOffset(Size,Size)}):Play()
	spawn(function()
		wait(2)
		Circle:Destroy()
	end)
end

local Material = {}

local Styles = {
	[1] = "Normal",
	[2] = "Invert",
	[3] = "Sheets"
}

local ThisTheme

local NavBar = {
	Normal = function()
		local NewNavBar = Objects.new("Round")
		NewNavBar.Name = "NavBar"
		NewNavBar.Size = UDim2.fromScale(1,0) + UDim2.fromOffset(-10,30)
		NewNavBar.Position = UDim2.fromOffset(5,35)
		NewNavBar.ImageColor3 = ThisTheme.NavBar
		NewNavBar.ZIndex = 100

		local NavBarShadow = Objects.new("Shadow")
		NavBarShadow.ImageColor3 = ThisTheme.NavBar
		NavBarShadow.Parent = NewNavBar
		NavBarShadow.ZIndex = 100

		local NavBarContent = Objects.new("Frame")
		NavBarContent.Name = "Content"
		NavBarContent.Parent = NewNavBar

		NavBarContent.ChildAdded:Connect(function(Child)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child, TweenInfo.new(1), {TextTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child, TweenInfo.new(1), {ImageTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child:FindFirstChildWhichIsA("ImageLabel"), TweenInfo.new(1), {ImageTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				Child.TextColor3 = ThisTheme.NavBarAccent
			end)
			pcall(function()
				Child:FindFirstChildWhichIsA("ImageLabel").ImageColor3 = ThisTheme.NavBarAccent
			end)
			pcall(function()
				Child.ImageColor3 = ThisTheme.NavBarAccent
			end)
		end)

		local NavBarList = Objects.new("UIListLayout")
		NavBarList.FillDirection = Enum.FillDirection.Horizontal
		NavBarList.HorizontalAlignment = Enum.HorizontalAlignment.Left
		NavBarList.VerticalAlignment = Enum.VerticalAlignment.Center
		NavBarList.SortOrder = Enum.SortOrder.LayoutOrder
		NavBarList.Parent = NavBarContent

		local NavBarPadding = Objects.new("UIPadding")
		NavBarPadding.PaddingLeft = UDim.new(0,5)
		NavBarPadding.Parent = NavBarContent

		return NewNavBar, NavBarContent
	end,
	Invert = function()
		local NewNavBar = Objects.new("Round")
		NewNavBar.Name = "NavBar"
		NewNavBar.Size = UDim2.fromScale(1,0) + UDim2.fromOffset(-10,30)
		NewNavBar.Position = UDim2.fromOffset(5,35)
		NewNavBar.ImageColor3 = ThisTheme.NavBarAccent
		NewNavBar.ImageTransparency = 1
		NewNavBar.ZIndex = 100

		local NavBarShadow = Objects.new("Shadow")
		NavBarShadow.ImageColor3 = ThisTheme.NavBarInvert
		NavBarShadow.ImageTransparency = 1
		NavBarShadow.Parent = NewNavBar
		NavBarShadow.ZIndex = 100

		TweenService:Create(NewNavBar, TweenInfo.new(1), {ImageTransparency = 0}):Play()
		TweenService:Create(NavBarShadow, TweenInfo.new(1), {ImageTransparency = 0}):Play()

		local NavBarContent = Objects.new("Frame")
		NavBarContent.Name = "Content"
		NavBarContent.Parent = NewNavBar

		NavBarContent.ChildAdded:Connect(function(Child)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child, TweenInfo.new(1), {TextTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child, TweenInfo.new(1), {ImageTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child:FindFirstChildWhichIsA("ImageLabel"), TweenInfo.new(1), {ImageTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				Child.TextColor3 = ThisTheme.NavBar
			end)
			pcall(function()
				Child:FindFirstChildWhichIsA("ImageLabel").ImageColor3 = ThisTheme.NavBar
			end)
			pcall(function()
				Child.ImageColor3 = ThisTheme.NavBar
			end)
		end)

		local NavBarList = Objects.new("UIListLayout")
		NavBarList.FillDirection = Enum.FillDirection.Horizontal
		NavBarList.HorizontalAlignment = Enum.HorizontalAlignment.Left
		NavBarList.VerticalAlignment = Enum.VerticalAlignment.Center
		NavBarList.SortOrder = Enum.SortOrder.LayoutOrder
		NavBarList.Parent = NavBarContent

		local NavBarPadding = Objects.new("UIPadding")
		NavBarPadding.PaddingLeft = UDim.new(0,5)
		NavBarPadding.Parent = NavBarContent

		return NewNavBar, NavBarContent
	end,
	Sheets = function()
		local NewNavBar = Objects.new("Round")
		NewNavBar.ClipsDescendants = true
		NewNavBar.Name = "NavBar"
		NewNavBar.Size = UDim2.fromScale(0,1) - UDim2.fromOffset(0,30)
		NewNavBar.Position = UDim2.fromOffset(0,30)
		NewNavBar.ImageColor3 = ThisTheme.NavBarAccent
		NewNavBar.ZIndex = 100

		local NavBarOverlay = Objects.new("Frame")
		NavBarOverlay.Name = "Overlay"
		NavBarOverlay.BackgroundColor3 = ThisTheme.NavBar
		NavBarOverlay.BackgroundTransparency = 1
		NavBarOverlay.Size = UDim2.fromScale(1,1) - UDim2.fromOffset(0,30)
		NavBarOverlay.Position = UDim2.fromOffset(0,30)
		NavBarOverlay.ZIndex = 75

		local NavBarMenu = Objects.new("NavBar")
		NavBarMenu.ZIndex = 100

		local NavBarShadow = Objects.new("Shadow")
		NavBarShadow.ImageColor3 = ThisTheme.NavBar
		NavBarShadow.Parent = NewNavBar
		NavBarShadow.ZIndex = 100

		local Effect1, Effect2, Effect3 = Objects.new("Frame"), Objects.new("Frame"), Objects.new("Frame")

		Effect1.ZIndex = 100
		Effect2.ZIndex = 100
		Effect3.ZIndex = 100

		Effect1.BackgroundTransparency = 0
		Effect2.BackgroundTransparency = 0
		Effect3.BackgroundTransparency = 0

		Effect1.BackgroundColor3 = ThisTheme.NavBarAccent
		Effect2.BackgroundColor3 = ThisTheme.NavBarAccent
		Effect3.BackgroundColor3 = ThisTheme.NavBar

		Effect1.Size = UDim2.fromScale(1,0) + UDim2.fromOffset(0,5)
		Effect2.Size = UDim2.fromScale(0,1) + UDim2.fromOffset(5,0)
		Effect3.Size = UDim2.fromScale(0,1) + UDim2.fromOffset(1,0)

		Effect1.Position = UDim2.fromScale(0,0)
		Effect2.Position = UDim2.fromScale(1,0) - UDim2.fromOffset(5,0)
		Effect3.Position = UDim2.fromScale(1,0)

		Effect1.Parent = NewNavBar
		Effect2.Parent = NewNavBar
		Effect3.Parent = NewNavBar

		local NavBarContent = Objects.new("Frame")
		NavBarContent.Name = "Content"
		NavBarContent.Parent = NewNavBar

		local NavBarList = Objects.new("UIListLayout")
		NavBarList.FillDirection = Enum.FillDirection.Vertical
		NavBarList.HorizontalAlignment = Enum.HorizontalAlignment.Center
		NavBarList.VerticalAlignment = Enum.VerticalAlignment.Top
		NavBarList.SortOrder = Enum.SortOrder.LayoutOrder
		NavBarList.Parent = NavBarContent

		local NavBarPadding = Objects.new("UIPadding")
		NavBarPadding.PaddingLeft = UDim.new(0,5)
		NavBarPadding.PaddingRight = UDim.new(0,5)
		NavBarPadding.PaddingTop = UDim.new(0,5)
		NavBarPadding.PaddingBottom = UDim.new(0,5)
		NavBarPadding.Parent = NavBarContent

		NavBarContent.ChildAdded:Connect(function(Child)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child, TweenInfo.new(1), {TextTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child, TweenInfo.new(1), {ImageTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				local Children = #NavBarContent:GetChildren() - 2
				TweenService:Create(Child:FindFirstChildWhichIsA("ImageLabel"), TweenInfo.new(1), {ImageTransparency = (Children > 1) and 0.5 or 0}):Play()
			end)
			pcall(function()
				Child.Size = UDim2.fromScale(1,0) + UDim2.fromOffset(0,30)
			end)
			pcall(function()
				Child:FindFirstChildWhichIsA("ImageLabel").ImageColor3 = ThisTheme.NavBar
			end)
			pcall(function()
				Child.TextColor3 = ThisTheme.NavBar
			end)
			pcall(function()
				Child.ImageColor3 = ThisTheme.NavBar
			end)
		end)

		return NewNavBar, NavBarContent, NavBarMenu,  NavBarOverlay
	end
}

local MainGUI

function TryAddMenu(Object, Menu, ReturnTable)
	local Menu = Menu
	local ReturnTable = ReturnTable
	ReturnTable.Object = Object
	local Total = 0

	table.foreach(Menu, function(_, Value)
		Total = Total + ((typeof(Value) == "function") and 1 or 0)
	end)

	if Total > 0 then
		local MenuToggle = false

		local MenuButton = Objects.new("Menu")
		MenuButton.ImageTransparency = 1
		MenuButton.Parent = Object

		TweenService:Create(MenuButton, TweenInfo.new(0.5), {ImageTransparency = 0}):Play()

		local Size = Total * 30 + ((Total + 1) * 2)

		local MenuBuild = Objects.new("Round")
		MenuBuild.Name = "Menu"
		MenuBuild.ImageColor3 = ThisTheme.ButtonAccent
		MenuBuild.Size = UDim2.fromOffset(120,0)
		MenuBuild.Position = UDim2.fromOffset(MenuButton.AbsolutePosition.X,MenuButton.AbsolutePosition.Y) - UDim2.fromOffset(125,5)
		MenuBuild.ZIndex = 100
		MenuBuild.ClipsDescendants = true
		MenuBuild.Parent = MainGUI

		MenuButton:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
			MenuBuild.Position = UDim2.fromOffset(MenuButton.AbsolutePosition.X,MenuButton.AbsolutePosition.Y) - UDim2.fromOffset(125,5)
		end)

		local MenuContent = Objects.new("Frame")
		MenuContent.Name = "Content"
		MenuContent.Parent = MenuBuild

		local MenuList = Objects.new("UIListLayout")
		MenuList.Padding = UDim.new(0,2)
		MenuList.Parent = MenuContent

		local MenuPadding = Objects.new("UIPadding")
		MenuPadding.PaddingTop = UDim.new(0,2)
		MenuPadding.PaddingRight = UDim.new(0,2)
		MenuPadding.PaddingLeft = UDim.new(0,2)
		MenuPadding.PaddingBottom = UDim.new(0,2)
		MenuPadding.Parent = MenuContent

		MenuButton.MouseButton1Down:Connect(function()
			MenuToggle = not MenuToggle
			TweenService:Create(MenuBuild, TweenInfo.new(0.15), {Size = MenuToggle and UDim2.fromOffset(120,Size) or UDim2.fromOffset(120,0)}):Play()
		end)

		table.foreach(Menu, function(Option, Value)
			if typeof(Value) == "function" then
				local MenuOption = Objects.new("SmoothButton")
				MenuOption.Name = "MenuOption"
				MenuOption.Size = UDim2.fromScale(1,0) + UDim2.fromOffset(0,30)
				MenuOption.ImageColor3 = ThisTheme.Button
				MenuOption.ImageTransparency = 1
				MenuOption.ZIndex = 150
				MenuOption.Parent = MenuContent

				local OptionShadow = Objects.new("Shadow")
				OptionShadow.ImageColor3 = ThisTheme.Button
				OptionShadow.ImageTransparency = 1
				OptionShadow.Parent = MenuOption

				local OptionValue = Objects.new("Label")
				OptionValue.Name = "Value"
				OptionValue.Position = UDim2.fromScale(0,0)
				OptionValue.Size = UDim2.fromScale(1,1) - UDim2.fromOffset(5,0)
				OptionValue.Text = Option
				OptionValue.TextColor3 = ThisTheme.Button
				OptionValue.Font = Enum.Font.Gotham
				OptionValue.TextSize = 12
				OptionValue.ZIndex = 150
				OptionValue.TextXAlignment = Enum.TextXAlignment.Right
				OptionValue.Parent = MenuOption

				MenuOption.MouseButton1Down:Connect(function()
					Value(ReturnTable)
					MenuToggle = false
					TweenService:Create(MenuBuild, TweenInfo.new(0.15), {Size = UDim2.fromOffset(120,0)}):Play()
				end)

				MenuOption.MouseEnter:Connect(function()
					TweenService:Create(MenuOption, TweenInfo.new(0.15), {ImageTransparency = 0.8}):Play()
					TweenService:Create(OptionShadow, TweenInfo.new(0.15), {ImageTransparency = 0.8}):Play()
				end)

				MenuOption.MouseLeave:Connect(function()
					TweenService:Create(MenuOption, TweenInfo.new(0.15), {ImageTransparency = 1}):Play()
					TweenService:Create(OptionShadow, TweenInfo.new(0.15), {ImageTransparency = 1}):Play()
				end)
			end
		end)
		return true, MenuButton
	end
	return false
end

function CreateNewButton(ButtonConfig, Parent)
	local ButtonText = ButtonConfig.Text or "nil button"
	local ButtonCallback = ButtonConfig.Callback or function() print("nil button") end
	local Menu = ButtonConfig.Menu or {}

	local Button = Objects.new("SmoothButton")
	Button.Name = "Button"
	Button.Size = UDim2.fromScale(1,0) + UDim2.fromOffset(0,30)
	Button.ImageColor3 = ThisTheme.Button
	Button.ImageTransparency = 1
	Button.Parent = Parent

	local ButtonShadow = Objects.new("Shadow")
	ButtonShadow.ImageColor3 = ThisTheme.Button
	ButtonShadow.ImageTransparency = 1
	ButtonShadow.Parent = Button

	local ButtonLabel = Objects.new("Label")
	ButtonLabel.Text = ButtonText
	ButtonLabel.TextColor3 = ThisTheme.ButtonAccent
	ButtonLabel.Font = Enum.Font.GothamSemibold
	ButtonLabel.TextSize = 14
	ButtonLabel.ClipsDescendants = true
	ButtonLabel.TextTransparency = 1
	ButtonLabel.Parent = Button

	TweenService:Create(Button, TweenInfo.new(0.5), {ImageTransparency = 0}):Play()
	TweenService:Create(ButtonShadow, TweenInfo.new(0.5), {ImageTransparency = 0}):Play()
	TweenService:Create(ButtonLabel, TweenInfo.new(0.5), {TextTransparency = 0}):Play()

	Button.MouseButton1Down:Connect(function()
		CircleAnim(ButtonLabel, ThisTheme.ButtonAccent, ThisTheme.Button)
		ButtonCallback()
	end)

	local MenuAdded = TryAddMenu(Button, Menu, {})

	return Button, ButtonLabel
end

function Material.Load(Config)
	local Style = (Config.Style and math.clamp(Config.Style, 1, 3)) or 1
	local Title = Config.Title or "MaterialLua"
	local SizeX = Config.SizeX or 300
	local SizeY = Config.SizeY or 500
	local Theme = Config.Theme or "Light"
	local Overrides = Config.ColorOverrides or {}
	local O
