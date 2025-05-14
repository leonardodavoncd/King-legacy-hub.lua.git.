local Settings = { AutoFarm = false, AutoQuest = false, AutoBoss = false, AutoSkill = false, AutoCollectDrops = false, AutoTeleport = false, SelectedIsland = nil, AutoBuyItems = false, HubOpen = true }

local Islands = { {Name = "Starter Island", Position = Vector3.new(100, 10, 200)}, {Name = "Pirate Island", Position = Vector3.new(300, 10, 500)}, {Name = "Marine Base", Position = Vector3.new(500, 10, 800)} }

function SelectIsland(name) for _, island in ipairs(Islands) do if island.Name == name then Settings.SelectedIsland = island.Position return end end end

function ToggleAutoBuyItems(state) Settings.AutoBuyItems = state end

function ToggleAutoTeleport(state) Settings.AutoTeleport = state if state and Settings.SelectedIsland then local player = game.Players.LocalPlayer if player and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then player.Character.HumanoidRootPart.CFrame = CFrame.new(Settings.SelectedIsland) end end end

function CloseHub() Settings.HubOpen = false end

print("Hub carregado com sucesso!")
