# Esp-para-blox-fruit--- Coloque este LocalScript em StarterPlayerScripts
local Players = game:GetService("Players")
local player = Players.LocalPlayer

local function addNameTag(character)
    local head = character:WaitForChild("Head", 5)
    if not head then return end

    -- Cria o BillboardGui
    local billboard = Instance.new("BillboardGui")
    billboard.Name = "LocalNameTag"
    billboard.Adornee = head
    billboard.Size = UDim2.new(0, 150, 0, 50)
    billboard.StudsOffset = Vector3.new(0, 2.5, 0)
    billboard.AlwaysOnTop = true
    billboard.Parent = player:WaitForChild("PlayerGui")

    -- Label dentro do BillboardGui
    local label = Instance.new("TextLabel", billboard)
    label.Size = UDim2.new(1, 0, 1, 0)
    label.BackgroundTransparency = 1
    label.Text = "Meu Nome: " .. player.Name
    label.TextScaled = true
    label.Font = Enum.Font.SourceSansBold
end

player.CharacterAdded:Connect(addNameTag)
if player.Character then
    addNameTag(player.Character)
end
