--[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
--[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local Title = Instance.new("TextLabel")
local ExecuteButton = Instance.new("TextButton")
local ClearButton = Instance.new("TextButton")
local InjectButton = Instance.new("TextButton")
local Notifier = Instance.new("TextLabel")
local ScriptBox = Instance.new("TextBox")

ScreenGui.Parent = game.CoreGui
Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.Size = UDim2.new(0, 400, 0, 300)
Frame.Position = UDim2.new(0.5, -200, 0.5, -150)
Frame.Active = true
Frame.Draggable = true

Title.Parent = Frame
Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Title.Size = UDim2.new(1, 0, 0, 50)
Title.Text = "ziverx ss" -- Updated title
Title.TextColor3 = Color3.fromRGB(0, 0, 0)
Title.TextScaled = true

ScriptBox.Parent = Frame
ScriptBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ScriptBox.Size = UDim2.new(1, 0, 0, 100)
ScriptBox.Position = UDim2.new(0, 0, 0, 50)
ScriptBox.PlaceholderText = "Enter your script here"

ExecuteButton.Parent = Frame
ExecuteButton.BackgroundColor3 = Color3.fromRGB(0, 170, 0)
ExecuteButton.Size = UDim2.new(0.48, 0, 0, 50)
ExecuteButton.Position = UDim2.new(0, 0, 0, 160)
ExecuteButton.Text = "Execute"

ClearButton.Parent = Frame
ClearButton.BackgroundColor3 = Color3.fromRGB(170, 0, 0)
ClearButton.Size = UDim2.new(0.48, 0, 0, 50)
ClearButton.Position = UDim2.new(0.52, 0, 0, 160)
ClearButton.Text = "Clear"

InjectButton.Parent = Frame
InjectButton.BackgroundColor3 = Color3.fromRGB(0, 0, 170)
InjectButton.Size = UDim2.new(1, 0, 0, 50)
InjectButton.Position = UDim2.new(0, 0, 0, 220)
InjectButton.Text = "Inject"

Notifier.Parent = Frame
Notifier.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Notifier.Size = UDim2.new(1, 0, 0, 50)
Notifier.Position = UDim2.new(0, 0, 0, 270)
Notifier.Text = ""
Notifier.TextColor3 = Color3.fromRGB(255, 0, 0)
Notifier.TextScaled = true

ExecuteButton.MouseButton1Click:Connect(function()
    local scriptToExecute = ScriptBox.Text
    if not scriptToExecute:find("backdoor") then
        Notifier.Text = "No backdoor detected!"
    else
        loadstring(scriptToExecute)()
        Notifier.Text = "Script Executed!"
    end
    wait(2)
    Notifier.Text = ""
end)

ClearButton.MouseButton1Click:Connect(function()
    ScriptBox.Text = ""
    Notifier.Text = "Script Cleared!"
    wait(2)
    Notifier.Text = ""
end)

InjectButton.MouseButton1Click:Connect(function()
    Notifier.Text = "Injection Logic Triggered!"
    wait(2)
    Notifier.Text = ""
end)

