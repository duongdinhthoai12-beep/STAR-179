LocalScript trong StarterGui
loadstring([[
local player = game.Players.LocalPlayer
local gui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
local button = Instance.new("TextButton")
button.Parent = gui
button.Text = "Jump"
button.Size = UDim2.new(0, 100, 0, 50)
button.Position = UDim2.new(0.8, 0, 0.8, 0)
button.BackgroundColor3 = Color3.fromRGB(0,170,255)
button.TextColor3 = Color3.fromRGB(255,255,255)
button.MouseButton1Click:Connect(function()
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:FindFirstChildOfClass("Humanoid")
if humanoid then
humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
end
end)
]])()
