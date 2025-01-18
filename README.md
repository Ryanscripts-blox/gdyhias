-- Configurações
local autoFarm = true
local autoBau = true
local autoFruta = true
local delay = 0.1

-- Funções
local function autoFarmFunction()
    if autoFarm then
        for i, v in pairs(game.Workspace:GetChildren()) do
            if v.Name == "Fruit" then
                game.ReplicatedStorage.FruitCollect:FireServer(v)
            elseif v.Name == "Tree" then
                game.ReplicatedStorage.TreeCut:FireServer(v)
            end
        end
    end
end

local function autoBauFunction()
    if autoBau then
        for i, v in pairs(game.Workspace:GetChildren()) do
            if v.Name == "Chest" then
                game.ReplicatedStorage.ChestOpen:FireServer(v)
            end
        end
    end
end

local function autoFrutaFunction()
    if autoFruta then
        for i, v in pairs(game.Workspace:GetChildren()) do
            if v.Name == "Fruit" then
                game.ReplicatedStorage.FruitEat:FireServer(v)
            end
        end
    end
end

-- Loop principal
while wait(delay) do
    autoFarmFunction()
    autoBauFunction()
    autoFrutaFunction()
end# gdyhias
