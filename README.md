local playerBlock = script.Parent
local userInputService = game:GetService("UserInputService")
local moveSpeed = 20 -- Adjust the speed of the block

local function onInputBegan(input, gameProcessed)
    if gameProcessed then return end

    if input.KeyCode == Enum.KeyCode.W then
        playerBlock.Position = playerBlock.Position + Vector3.new(0, 0, -moveSpeed)
    elseif input.KeyCode == Enum.KeyCode.S then
        playerBlock.Position = playerBlock.Position + Vector3.new(0, 0, moveSpeed)
    elseif input.KeyCode == Enum.KeyCode.A then
        playerBlock.Position = playerBlock.Position + Vector3.new(-moveSpeed, 0, 0)
    elseif input.KeyCode == Enum.KeyCode.D then
        playerBlock.Position = playerBlock.Position + Vector3.new(moveSpeed, 0, 0)
    end
end

userInputService.InputBegan:Connect(onInputBegan)

