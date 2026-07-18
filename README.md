-- ZeCoordinates: Pequena ferramenta de captura de coordenadas
local ScreenGui = Instance.new("ScreenGui", game.Players.LocalPlayer:WaitForChild("PlayerGui"))
local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 180, 0, 100)
Frame.Position = UDim2.new(0.8, 0, 0.2, 0)
Frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
Frame.Active = true
Frame.Draggable = true -- Pode arrastar

local Title = Instance.new("TextLabel", Frame)
Title.Size = UDim2.new(1, 0, 0, 30)
Title.Text = "Captura do Zé"
Title.TextColor3 = Color3.new(1, 1, 1)
Title.BackgroundTransparency = 1

local Btn = Instance.new("TextButton", Frame)
Btn.Size = UDim2.new(0.8, 0, 0, 40)
Btn.Position = UDim2.new(0.1, 0, 0.4, 0)
Btn.Text = "Copiar Posição"
Btn.BackgroundColor3 = Color3.fromRGB(255, 140, 0)
Btn.TextColor3 = Color3.new(1, 1, 1)

Btn.MouseButton1Click:Connect(function()
    local pos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
    local cframeStr = string.format("CFrame.new(%f, %f, %f)", pos.X, pos.Y, pos.Z)
    setclipboard(cframeStr)
    Btn.Text = "Copiado!"
    task.wait(1)
    Btn.Text = "Copiar Posição"
end)
