local Lighting = game:GetService("Lighting")
local SKY_ID = "rbxassetid://358313209"

local function ApplySky()
    -- remove qualquer sky antigo
    for _, obj in ipairs(Lighting:GetChildren()) do
        if obj:IsA("Sky") then
            obj:Destroy()
        end
    end

    -- cria o novo sky
    local newSky = Instance.new("Sky")
    newSky.Name = "GlobalSky"

    newSky.SkyboxBk = SKY_ID
    newSky.SkyboxDn = SKY_ID
    newSky.SkyboxFt = SKY_ID
    newSky.SkyboxLf = SKY_ID
    newSky.SkyboxRt = SKY_ID
    newSky.SkyboxUp = SKY_ID

    newSky.Parent = Lighting
end

-- executa automaticamente assim que o servidor iniciar
ApplySky()
