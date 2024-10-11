
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local workspace = game:GetService("Workspace")


local function coletarFrutas()
    for _, fruta in pairs(workspace:GetChildren()) do
        if fruta:IsA("Tool") and fruta.Name:match("Fruit") then
            humanoid:MoveTo(fruta.Position)
            wait(1)
            fireclickdetector(fruta:FindFirstChildOfClass("ClickDetector"))
        end
    end
end


local function coletarBaus()
    for _, bau in pairs(workspace:GetChildren()) do
        if bau:IsA("Model") and bau.Name:match("Chest") then
            humanoid:MoveTo(bau.PrimaryPart.Position)
            wait(1)
            fireclickdetector(bau:FindFirstChildOfClass("ClickDetector"))
        end
    end
end


local function coletarFragmentos()
    for _, fragmento in pairs(workspace:GetChildren()) do
        if fragmento:IsA("Part") and fragmento.Name:match("Fragment") then
            humanoid:MoveTo(fragmento.Position)
            wait(1)
            fireclickdetector(fragmento:FindFirstChildOfClass("ClickDetector"))
        end
    end
end


coletarFrutas()
coletarBaus()
coletarFragmentos()


