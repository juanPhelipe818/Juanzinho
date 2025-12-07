-- Altera o céu e atmosfera para todos os jogadores
local Lighting = game:GetService("Lighting")

-- Criar um novo Sky (substitui o padrão)
local sky = Instance.new("Sky")
sky.Name = "CustomSky"
sky.SkyboxBk = "http://www.roblox.com/asset/?id=358313209"
sky.SkyboxDn = "http://www.roblox.com/asset/?id=358313209"
sky.SkyboxFt = "http://www.roblox.com/asset/?id=358313209"
sky.SkyboxLf = "http://www.roblox.com/asset/?id=358313209"
sky.SkyboxRt = "http://www.roblox.com/asset/?id=358313209"
sky.SkyboxUp = "http://www.roblox.com/asset/?id=358313209"
sky.Parent = Lighting

-- Editar Atmosphere
local atmosphere = Lighting:FindFirstChildOfClass("Atmosphere")
if not atmosphere then
    atmosphere = Instance.new("Atmosphere", Lighting)
end

atmosphere.Density = 0.3
atmosphere.Offset = 0.25
atmosphere.Color = Color3.fromRGB(199, 199, 199)
atmosphere.Decay = Color3.fromRGB(106, 112, 124)
atmosphere.Glare = 0
atmosphere.Haze = 0
