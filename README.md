local MINIGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local Page1 = Instance.new("ScrollingFrame")
local ProfileName = Instance.new("TextLabel")
local ProfileImage = Instance.new("ImageLabel")
local UICorner_2 = Instance.new("UICorner")
local Uen = Instance.new("TextLabel")
local Logo = Instance.new("ImageLabel")
local NameHub = Instance.new("TextLabel")
local UserInputService = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")
local RunService = game:GetService("RunService")
local LocalPlayer = game:GetService("Players").LocalPlayer
local Mouse = LocalPlayer:GetMouse()
function dragify(Frame, object)
    dragToggle = nil
    dragSpeed = .25
    dragInput = nil
    dragStart = nil
    dragPos = nil
    function updateInput(input)
        Delta = input.Position - dragStart
        Position =
            UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
        game:GetService("TweenService"):Create(object, TweenInfo.new(dragSpeed), {Position = Position}):Play()
    end
    Frame.InputBegan:Connect(
        function(input)
            if
                (input.UserInputType == Enum.UserInputType.MouseButton1 or
                    input.UserInputType == Enum.UserInputType.Touch)
            then
                dragToggle = true
                dragStart = input.Position
                startPos = object.Position
                input.Changed:Connect(
                    function()
                        if (input.UserInputState == Enum.UserInputState.End) then
                            dragToggle = false
                        end
                    end
                )
            end
        end
    )
    Frame.InputChanged:Connect(
        function(input)
            if
                (input.UserInputType == Enum.UserInputType.MouseMovement or
                    input.UserInputType == Enum.UserInputType.Touch)
            then
                dragInput = input
            end
        end
    )
    game:GetService("UserInputService").InputChanged:Connect(
    function(input)
        if (input == dragInput and dragToggle) then
            updateInput(input)
        end
    end
    )
end
MINIGui.Name = "MINIGui"
MINIGui.Parent = game.CoreGui
MINIGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

MainFrame.Name = "MainFrame"
MainFrame.Parent = MINIGui
MainFrame.BackgroundColor3 = Color3.fromRGB(11, 11, 11)
MainFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.BorderSizePixel = 0
MainFrame.Position = UDim2.new(0.234014496, 0, 0.157568231, 0)
MainFrame.Size = UDim2.new(0.543836534, 0, 0.585607946, 0)

UICorner.Parent = MainFrame

Page1.Name = "Page1"
Page1.Parent = MainFrame
Page1.Active = true
Page1.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
Page1.BorderColor3 = Color3.fromRGB(0, 0, 0)
Page1.BorderSizePixel = 0
Page1.Position = UDim2.new(4.0420634e-08, 0, 0.119897962, 0)
Page1.Size = UDim2.new(0.99999994, 0, 0.880102038, 0)

ProfileName.Name = "ProfileName"
ProfileName.Parent = Page1
ProfileName.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.BackgroundTransparency = 1.060
ProfileName.BorderColor3 = Color3.fromRGB(0, 0, 0)
ProfileName.BorderSizePixel = 0
ProfileName.Position = UDim2.new(0.204983577, 0, 0.0619276464, 0)
ProfileName.Size = UDim2.new(0.315359414, 0, 0.0481454171, 0)
ProfileName.Font = Enum.Font.SourceSans
ProfileName.Text = "Name : "..game.Players.LocalPlayer.Name
ProfileName.TextColor3 = Color3.fromRGB(255, 255, 255)
ProfileName.TextScaled = true
ProfileName.TextSize = 14.000
ProfileName.TextWrapped = true

ProfileImage.Name = "ProfileImage"
ProfileImage.Parent = Page1
ProfileImage.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ProfileImage.BorderColor3 = Color3.fromRGB(0, 0, 0)
ProfileImage.BorderSizePixel = 0
ProfileImage.Position = UDim2.new(0.0266842209, 0, 0.0199443586, 0)
ProfileImage.Size = UDim2.new(0.167383075, 0, 0.136916906, 0)
ProfileImage.Image = "https://www.roblox.com/headshot-thumbnail/image?userId=" .. game.Players.LocalPlayer.UserId .. "&width=420&height=420&format=png"

UICorner_2.CornerRadius = UDim.new(0, 100)
UICorner_2.Parent = ProfileImage

Uen.Name = "Uen"
Uen.Parent = Page1
Uen.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Uen.BackgroundTransparency = 1.000
Uen.BorderColor3 = Color3.fromRGB(0, 0, 0)
Uen.BorderSizePixel = 0
Uen.Position = UDim2.new(0.344469488, 0, 0.355465084, 0)
Uen.Size = UDim2.new(0.266842574, 0, -0.0770326704, 0)
Uen.Font = Enum.Font.SourceSans
Uen.Text = "ทำของเดียวก็รู้"
Uen.TextColor3 = Color3.fromRGB(0, 112, 0)
Uen.TextScaled = true
Uen.TextSize = 14.000
Uen.TextWrapped = true
dragify(MainFrame, MainFrame)
Logo.Name = "Logo"
Logo.Parent = MainFrame
Logo.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Logo.BorderColor3 = Color3.fromRGB(0, 0, 0)
Logo.BorderSizePixel = 0
Logo.Position = UDim2.new(0.0109090907, 0, -0.00211862801, 0)
Logo.Size = UDim2.new(0.0966887474, 0, 0.119897969, 0)
Logo.Image = "rbxassetid://15640661640"

NameHub.Name = "NameHub"
NameHub.Parent = MainFrame
NameHub.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
NameHub.BackgroundTransparency = 1.000
NameHub.BorderColor3 = Color3.fromRGB(0, 0, 0)
NameHub.BorderSizePixel = 0
NameHub.Position = UDim2.new(0.302307755, 0, -0.00714447536, 0)
NameHub.Size = UDim2.new(0.371153742, 0, 0.127118647, 0)
NameHub.Font = Enum.Font.SourceSans
NameHub.Text = "Attack Hub - Kaitun PC"
NameHub.TextColor3 = Color3.fromRGB(255, 255, 255)
NameHub.TextScaled = true
NameHub.TextSize = 14.000
NameHub.TextWrapped = true
