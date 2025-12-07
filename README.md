-- Cria pasta + script automaticamente no ServerScriptService com o sky solicitado

local SSS = game:GetService("ServerScriptService")

-- Criar pasta
local folder = Instance.new("Folder")
folder.Name = "SkyChanger"
folder.Parent = SSS

-- Criar conteúdo do Script
local scriptCode = [[
local Lighting = game:GetService("Lighting")
local SKY_ID = "rbxassetid://358313209" -- Sky do link que você enviou

local function ApplySky()
    -- Remove Sky antigo
    for _, obj in ipairs(Lighting:GetChildren()) do
        if obj:IsA("Sky") then
            obj:Destroy()
        end
    end

    -- Cria o novo Sky
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

-- Aplica automaticamente
ApplySky()
]]

-- Criar Script no ServerScriptService
local newScript = Instance.new("Script")
newScript.Name = "AutoSkyChanger"
newScript.Source = scriptCode
newScript.Parent = folder

print("Pasta + Script criados com sucesso em ServerScriptService!")
