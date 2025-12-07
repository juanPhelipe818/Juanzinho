-- Script para alterar o Sky global do jogo
-- Coloque em: ServerScriptService

local Lighting = game:GetService("Lighting")

-- Remove qualquer Sky antigo
local oldSkies = Lighting:GetChildren()
for _, v in ipairs(oldSkies) do
    if v:IsA("Sky") then
        v:Destroy()
    end
end

-- Cria o novo Sky usando o ID solicitado
local sky = Instance.new("Sky")
sky.Name = "NewSky"
sky.SkyboxBk = "rbxassetid://358313209"
sky.SkyboxDn = "rbxassetid://358313209"
sky.SkyboxFt = "rbxassetid://358313209"
sky.SkyboxLf = "rbxassetid://358313209"
sky.SkyboxRt = "rbxassetid://358313209"
sky.SkyboxUp = "rbxassetid://358313209"
sky.Parent = Lighting

print("Novo Sky aplicado com sucesso!")
