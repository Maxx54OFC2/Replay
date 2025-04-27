local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local Workspace = game:GetService("Workspace")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- Criar pasta CarsReplay em ReplicatedStorage
local carsReplayFolder = Instance.new("Folder")
carsReplayFolder.Name = "CarsReplay"
carsReplayFolder.Parent = ReplicatedStorage

-- Criar ScreenGui
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = playerGui
screenGui.Enabled = true

-- Criar Botão Principal
local mainButton = Instance.new("TextButton")
mainButton.Size = UDim2.new(0, 50, 0, 50)
mainButton.Position = UDim2.new(0.1, 0, 0.1, 0)
mainButton.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
mainButton.Text = "+"
mainButton.TextColor3 = Color3.fromRGB(255, 255, 255)
mainButton.TextScaled = true
mainButton.Parent = screenGui
mainButton.Draggable = true
mainButton.Active = true
mainButton.Selectable = true
mainButton.Visible = true

local mainButtonCorner = Instance.new("UICorner")
mainButtonCorner.CornerRadius = UDim.new(0, 8)
mainButtonCorner.Parent = mainButton

local mainButtonStroke = Instance.new("UIStroke")
mainButtonStroke.Color = Color3.fromRGB(88, 137, 192)
mainButtonStroke.Thickness = 2
mainButtonStroke.Parent = mainButton

local mainButtonTextStroke = Instance.new("UIStroke")
mainButtonTextStroke.Color = Color3.fromRGB(25, 45, 58)
mainButtonTextStroke.Thickness = 1
mainButtonTextStroke.Parent = mainButton

-- Criar Frame do Menu Principal
local mainMenuFrame = Instance.new("Frame")
mainMenuFrame.Size = UDim2.new(0, 200, 0, 120)
mainMenuFrame.Position = UDim2.new(0.1, 60, 0, 10)
mainMenuFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
mainMenuFrame.Visible = false
mainMenuFrame.Active = true
mainMenuFrame.Parent = screenGui

local mainMenuFrameCorner = Instance.new("UICorner")
mainMenuFrameCorner.CornerRadius = UDim.new(0, 12)
mainMenuFrameCorner.Parent = mainMenuFrame

local mainMenuFrameStroke = Instance.new("UIStroke")
mainMenuFrameStroke.Color = Color3.fromRGB(88, 137, 192)
mainMenuFrameStroke.Thickness = 1
mainMenuFrameStroke.Parent = mainMenuFrame

-- Botão para abrir o menu Replay
local replayMenuButton = Instance.new("TextButton")
replayMenuButton.Size = UDim2.new(0, 160, 0, 40)
replayMenuButton.Position = UDim2.new(0, 20, 0, 20)
replayMenuButton.BackgroundColor3 = Color3.fromRGB(88, 137, 192)
replayMenuButton.Text = "Replay"
replayMenuButton.TextColor3 = Color3.fromRGB(25, 45, 58)
replayMenuButton.TextScaled = true
replayMenuButton.Font = Enum.Font.SourceSansBold
replayMenuButton.Parent = mainMenuFrame

local replayMenuButtonCorner = Instance.new("UICorner")
replayMenuButtonCorner.CornerRadius = UDim.new(0, 8)
replayMenuButtonCorner.Parent = replayMenuButton

local replayMenuButtonStroke = Instance.new("UIStroke")
replayMenuButtonStroke.Color = Color3.fromRGB(255, 255, 255)
replayMenuButtonStroke.Thickness = 1
replayMenuButtonStroke.Parent = replayMenuButton

-- Botão para abrir o menu Replays
local replaysMenuButton = Instance.new("TextButton")
replaysMenuButton.Size = UDim2.new(0, 160, 0, 40)
replaysMenuButton.Position = UDim2.new(0, 20, 0, 70)
replaysMenuButton.BackgroundColor3 = Color3.fromRGB(88, 137, 192)
replaysMenuButton.Text = "Replays"
replaysMenuButton.TextColor3 = Color3.fromRGB(25, 45, 58)
replaysMenuButton.TextScaled = true
replaysMenuButton.Font = Enum.Font.SourceSansBold
replaysMenuButton.Parent = mainMenuFrame

local replaysMenuButtonCorner = Instance.new("UICorner")
replaysMenuButtonCorner.CornerRadius = UDim.new(0, 8)
replaysMenuButtonCorner.Parent = replaysMenuButton

local replaysMenuButtonStroke = Instance.new("UIStroke")
replaysMenuButtonStroke.Color = Color3.fromRGB(255, 255, 255)
replaysMenuButtonStroke.Thickness = 1
replaysMenuButtonStroke.Parent = replaysMenuButton

-- Criar Frame do Menu Replay
local replayFrame = Instance.new("Frame")
replayFrame.Size = UDim2.new(0, 350, 0, 300)
replayFrame.Position = UDim2.new(0.1, 60, 0, 10)
replayFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
replayFrame.Visible = false
replayFrame.Active = true
replayFrame.Parent = screenGui

local replayFrameCorner = Instance.new("UICorner")
replayFrameCorner.CornerRadius = UDim.new(0, 12)
replayFrameCorner.Parent = replayFrame

local replayFrameStroke = Instance.new("UIStroke")
replayFrameStroke.Color = Color3.fromRGB(88, 137, 192)
replayFrameStroke.Thickness = 1
replayFrameStroke.Parent = replayFrame

-- Título "Replay"
local titleLabel = Instance.new("TextLabel")
titleLabel.Size = UDim2.new(1, 0, 0, 30)
titleLabel.Position = UDim2.new(0, 0, 0, 5)
titleLabel.BackgroundTransparency = 1
titleLabel.Text = "Replay"
titleLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
titleLabel.TextScaled = true
titleLabel.Font = Enum.Font.SourceSansBold
titleLabel.Parent = replayFrame

local titleLabelStroke = Instance.new("UIStroke")
titleLabelStroke.Color = Color3.fromRGB(25, 45, 58)
titleLabelStroke.Thickness = 1
titleLabelStroke.Parent = titleLabel

-- Contador de Tempo
local timeLabel = Instance.new("TextLabel")
timeLabel.Size = UDim2.new(0, 200, 0, 30)
timeLabel.Position = UDim2.new(0, 75, 0, 50)
timeLabel.BackgroundTransparency = 1
timeLabel.Text = "00:00:000"
timeLabel.TextColor3 = Color3.fromRGB(220, 220, 220)
timeLabel.TextScaled = true
timeLabel.Font = Enum.Font.SourceSansBold
timeLabel.Parent = replayFrame

local timeLabelStroke = Instance.new("UIStroke")
timeLabelStroke.Color = Color3.fromRGB(25, 45, 58)
timeLabelStroke.Thickness = 1
timeLabelStroke.Parent = timeLabel

-- Botão Play
local playButton = Instance.new("TextButton")
playButton.Size = UDim2.new(0, 100, 0, 40)
playButton.Position = UDim2.new(0, 20, 0, 90)
playButton.BackgroundColor3 = Color3.fromRGB(88, 137, 192)
playButton.Text = "Play"
playButton.TextColor3 = Color3.fromRGB(25, 45, 58)
playButton.TextScaled = true
playButton.Font = Enum.Font.SourceSansBold
playButton.Parent = replayFrame

local playButtonCorner = Instance.new("UICorner")
playButtonCorner.CornerRadius = UDim.new(0, 8)
playButtonCorner.Parent = playButton

local playButtonStroke = Instance.new("UIStroke")
playButtonStroke.Color = Color3.fromRGB(255, 255, 255)
playButtonStroke.Thickness = 1
playButtonStroke.Parent = playButton

-- Botão Clear
local clearButton = Instance.new("TextButton")
clearButton.Size = UDim2.new(0, 100, 0, 40)
clearButton.Position = UDim2.new(0, 230, 0, 90)
clearButton.BackgroundColor3 = Color3.fromRGB(200, 0, 0)
clearButton.Text = "Clear"
clearButton.TextColor3 = Color3.fromRGB(255, 255, 255)
clearButton.TextScaled = true
clearButton.Font = Enum.Font.SourceSansBold
clearButton.Parent = replayFrame

local clearButtonCorner = Instance.new("UICorner")
clearButtonCorner.CornerRadius = UDim.new(0, 8)
clearButtonCorner.Parent = clearButton

local clearButtonStroke = Instance.new("UIStroke")
clearButtonStroke.Color = Color3.fromRGB(255, 255, 255)
clearButtonStroke.Thickness = 1
clearButtonStroke.Parent = clearButton

-- Botão Replay
local replayButton = Instance.new("TextButton")
replayButton.Size = UDim2.new(0, 100, 0, 40)
replayButton.Position = UDim2.new(0, 125, 0, 140)
replayButton.BackgroundColor3 = Color3.fromRGB(88, 137, 192)
replayButton.Text = "Replay"
replayButton.TextColor3 = Color3.fromRGB(25, 45, 58)
replayButton.TextScaled = true
replayButton.Font = Enum.Font.SourceSansBold
replayButton.Parent = replayFrame

local replayButtonCorner = Instance.new("UICorner")
replayButtonCorner.CornerRadius = UDim.new(0, 8)
replayButtonCorner.Parent = replayButton

local replayButtonStroke = Instance.new("UIStroke")
replayButtonStroke.Color = Color3.fromRGB(255, 255, 255)
replayButtonStroke.Thickness = 1
replayButtonStroke.Parent = replayButton

-- Botão Save (novo)
local saveButton = Instance.new("TextButton")
saveButton.Size = UDim2.new(0, 100, 0, 40)
saveButton.Position = UDim2.new(0, 125, 0, 190)
saveButton.BackgroundColor3 = Color3.fromRGB(0, 200, 0)
saveButton.Text = "Save"
saveButton.TextColor3 = Color3.fromRGB(255, 255, 255)
saveButton.TextScaled = true
saveButton.Font = Enum.Font.SourceSansBold
saveButton.Parent = replayFrame

local saveButtonCorner = Instance.new("UICorner")
saveButtonCorner.CornerRadius = UDim.new(0, 8)
saveButtonCorner.Parent = saveButton

local saveButtonStroke = Instance.new("UIStroke")
saveButtonStroke.Color = Color3.fromRGB(255, 255, 255)
saveButtonStroke.Thickness = 1
saveButtonStroke.Parent = saveButton

-- Criar Frame do Menu Replays
local replaysFrame = Instance.new("Frame")
replaysFrame.Size = UDim2.new(0, 400, 0, 300)
replaysFrame.Position = UDim2.new(0.1, 60, 0, 10)
replaysFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
replaysFrame.Visible = false
replaysFrame.Active = true
replaysFrame.Parent = screenGui

local replaysFrameCorner = Instance.new("UICorner")
replaysFrameCorner.CornerRadius = UDim.new(0, 12)
replaysFrameCorner.Parent = replaysFrame

local replaysFrameStroke = Instance.new("UIStroke")
replaysFrameStroke.Color = Color3.fromRGB(88, 137, 192)
replaysFrameStroke.Thickness = 1
replaysFrameStroke.Parent = replaysFrame

-- Título "Replays"
local replaysTitleLabel = Instance.new("TextLabel")
replaysTitleLabel.Size = UDim2.new(1, 0, 0, 30)
replaysTitleLabel.Position = UDim2.new(0, 0, 0, 5)
replaysTitleLabel.BackgroundTransparency = 1
replaysTitleLabel.Text = "Replays"
replaysTitleLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
replaysTitleLabel.TextScaled = true
replaysTitleLabel.Font = Enum.Font.SourceSansBold
replaysTitleLabel.Parent = replaysFrame

local replaysTitleLabelStroke = Instance.new("UIStroke")
replaysTitleLabelStroke.Color = Color3.fromRGB(25, 45, 58)
replaysTitleLabelStroke.Thickness = 1
replaysTitleLabelStroke.Parent = replaysTitleLabel

-- ScrollingFrame para listar replays
local replaysScrollingFrame = Instance.new("ScrollingFrame")
replaysScrollingFrame.Size = UDim2.new(0, 380, 0, 250)
replaysScrollingFrame.Position = UDim2.new(0, 10, 0, 40)
replaysScrollingFrame.BackgroundTransparency = 1
replaysScrollingFrame.ScrollBarThickness = 5
replaysScrollingFrame.CanvasSize = UDim2.new(0, 0, 0, 0)
replaysScrollingFrame.Parent = replaysFrame

local replaysScrollingFrameLayout = Instance.new("UIListLayout")
replaysScrollingFrameLayout.Padding = UDim.new(0, 10)
replaysScrollingFrameLayout.Parent = replaysScrollingFrame

-- Frame para pop-up de salvamento
local savePopupFrame = Instance.new("Frame")
savePopupFrame.Size = UDim2.new(0, 300, 0, 200)
savePopupFrame.Position = UDim2.new(0.5, -150, 0.5, -100)
savePopupFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
savePopupFrame.Visible = false
savePopupFrame.Parent = screenGui

local savePopupFrameCorner = Instance.new("UICorner")
savePopupFrameCorner.CornerRadius = UDim.new(0, 12)
savePopupFrameCorner.Parent = savePopupFrame

local savePopupFrameStroke = Instance.new("UIStroke")
savePopupFrameStroke.Color = Color3.fromRGB(88, 137, 192)
savePopupFrameStroke.Thickness = 1
savePopupFrameStroke.Parent = savePopupFrame

-- Título do pop-up
local savePopupTitle = Instance.new("TextLabel")
savePopupTitle.Size = UDim2.new(1, 0, 0, 30)
savePopupTitle.Position = UDim2.new(0, 0, 0, 5)
savePopupTitle.BackgroundTransparency = 1
savePopupTitle.Text = "Save Replay"
savePopupTitle.TextColor3 = Color3.fromRGB(200, 200, 200)
savePopupTitle.TextScaled = true
savePopupTitle.Font = Enum.Font.SourceSansBold
savePopupTitle.Parent = savePopupFrame

-- Campo de entrada para nome do replay
local replayNameInput = Instance.new("TextBox")
replayNameInput.Size = UDim2.new(0, 260, 0, 40)
replayNameInput.Position = UDim2.new(0, 20, 0, 50)
replayNameInput.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
replayNameInput.Text = "Replay Name"
replayNameInput.TextColor3 = Color3.fromRGB(200, 200, 200)
replayNameInput.TextScaled = true
replayNameInput.Font = Enum.Font.SourceSans
replayNameInput.Parent = savePopupFrame

local replayNameInputCorner = Instance.new("UICorner")
replayNameInputCorner.CornerRadius = UDim.new(0, 8)
replayNameInputCorner.Parent = replayNameInput

local replayNameInputStroke = Instance.new("UIStroke")
replayNameInputStroke.Color = Color3.fromRGB(88, 137, 192)
replayNameInputStroke.Thickness = 1
replayNameInputStroke.Parent = replayNameInput

-- Campo de entrada para nome do carro
local carNameInput = Instance.new("TextBox")
carNameInput.Size = UDim2.new(0, 260, 0, 40)
carNameInput.Position = UDim2.new(0, 20, 0, 100)
carNameInput.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
carNameInput.Text = "Car Name"
carNameInput.TextColor3 = Color3.fromRGB(200, 200, 200)
carNameInput.TextScaled = true
carNameInput.Font = Enum.Font.SourceSans
carNameInput.Parent = savePopupFrame

local carNameInputCorner = Instance.new("UICorner")
carNameInputCorner.CornerRadius = UDim.new(0, 8)
carNameInputCorner.Parent = carNameInput

local carNameInputStroke = Instance.new("UIStroke")
carNameInputStroke.Color = Color3.fromRGB(88, 137, 192)
carNameInputStroke.Thickness = 1
carNameInputStroke.Parent = carNameInput

-- Botão para confirmar salvamento
local confirmSaveButton = Instance.new("TextButton")
confirmSaveButton.Size = UDim2.new(0, 100, 0, 40)
confirmSaveButton.Position = UDim2.new(0, 100, 0, 150)
confirmSaveButton.BackgroundColor3 = Color3.fromRGB(0, 200, 0)
confirmSaveButton.Text = "Confirm"
confirmSaveButton.TextColor3 = Color3.fromRGB(255, 255, 255)
confirmSaveButton.TextScaled = true
confirmSaveButton.Font = Enum.Font.SourceSansBold
confirmSaveButton.Parent = savePopupFrame

local confirmSaveButtonCorner = Instance.new("UICorner")
confirmSaveButtonCorner.CornerRadius = UDim.new(0, 8)
confirmSaveButtonCorner.Parent = confirmSaveButton

local confirmSaveButtonStroke = Instance.new("UIStroke")
confirmSaveButtonStroke.Color = Color3.fromRGB(255, 255, 255)
confirmSaveButtonStroke.Thickness = 1
confirmSaveButtonStroke.Parent = confirmSaveButton

-- Variáveis de controle
local isRecording = false
local recordings = {}
local savedReplays = {}
local startTime = 0
local elapsedTime = 0
local heartbeatConnection
local replayConnection
local currentReplayCarModel = nil

-- Função para formatar o tempo (MM:SS:MMM)
local function formatTime(timeInSeconds)
	local minutes = math.floor(timeInSeconds / 60)
	local seconds = math.floor(timeInSeconds % 60)
	local milliseconds = math.floor((timeInSeconds % 1) * 1000)
	return string.format("%02d:%02d:%03d", minutes, seconds, milliseconds)
end

-- Função para atualizar o contador de tempo
local function updateTimeLabel()
	if isRecording then
		elapsedTime = tick() - startTime
		timeLabel.Text = formatTime(elapsedTime)
	end
end

-- Função para encontrar o carro do jogador
local function getPlayerCar()
	local carCollection = Workspace:FindFirstChild("CarCollection")
	if carCollection then
		local playerCar = carCollection:FindFirstChild(player.Name)
		if playerCar then
			return playerCar:FindFirstChild("Car")
		end
	end
	return nil
end

-- Função para gerar um identificador único para partes
local function getUniquePartId(part, index)
	return part.Name .. "_" .. index
end

-- Função para obter o próximo nome de ReplayCar
local function getNextReplayCarName()
	local carCount = 0
	for _, obj in pairs(carsReplayFolder:GetChildren()) do
		if obj.Name:match("^ReplayCar(%d+)$") then
			local num = tonumber(obj.Name:match("^ReplayCar(%d+)$"))
			carCount = math.max(carCount, num)
		end
	end
	return "ReplayCar" .. (carCount + 1)
end

-- Função para gravar ações de todas as partes
local function recordAllPartsActions()
	local car = getPlayerCar()
	if not car then
		playButton.Text = "No Car!"
		task.wait(1)
		playButton.Text = isRecording and "Stop" or "Play"
		isRecording = false
		if heartbeatConnection then
			heartbeatConnection:Disconnect()
		end
		return
	end

	local partsData = {}
	local partIndex = {}
	for _, part in pairs(car:GetDescendants()) do
		if part:IsA("BasePart") then
			local partName = part.Name
			partIndex[partName] = (partIndex[partName] or 0) + 1
			local uniqueId = getUniquePartId(part, partIndex[partName])
			partsData[uniqueId] = part.CFrame
		end
	end

	if next(partsData) == nil then
		playButton.Text = "No Parts!"
		task.wait(1)
		playButton.Text = isRecording and "Stop" or "Play"
		isRecording = false
		if heartbeatConnection then
			heartbeatConnection:Disconnect()
		end
		return
	end

	local currentTime = tick() - startTime
	table.insert(recordings, {
		time = currentTime,
		parts = partsData
	})
end

-- Função para duplicar o carro (para replays)
local function duplicateCar(carModel)
	if not carModel then
		return nil
	end

	local carCopy = carModel:Clone()
	local cloneCount = 0
	local existingClones = {}
	for _, obj in pairs(Workspace:GetChildren()) do
		if obj.Name == "Clone" or obj.Name:match("^Clone%d+$") then
			existingClones[obj.Name] = true
			if obj.Name:match("^Clone(%d+)$") then
				local num = tonumber(obj.Name:match("^Clone(%d+)$"))
				cloneCount = math.max(cloneCount, num + 1)
			else
				cloneCount = math.max(cloneCount, 1)
			end
		end
	end
	carCopy.Name = not existingClones["Clone"] and cloneCount == 0 and "Clone" or "Clone" .. cloneCount
	for _, part in pairs(carCopy:GetDescendants()) do
		if part:IsA("BasePart") then
			part.Anchored = true
			part.CanCollide = false
		elseif part:IsA("VehicleSeat") then
			part.Disabled = true
		elseif part:IsA("BodyVelocity") or part:IsA("BodyGyro") or part:IsA("CylindricalConstraint") or part:IsA("HingeConstraint") then
			part:Destroy()
		end
	end
	carCopy.Parent = Workspace
	return carCopy
end

-- Função para clonar e salvar o carro em CarsReplay
local function saveCarModel()
	local car = getPlayerCar()
	if not car then
		return nil
	end

	local carCopy = car:Clone()
	carCopy.Name = getNextReplayCarName()
	for _, part in pairs(carCopy:GetDescendants()) do
		if part:IsA("BasePart") then
			part.Anchored = false
			part.CanCollide = false
		elseif part:IsA("VehicleSeat") then
			part.Disabled = true
		elseif part:IsA("BodyVelocity") or part:IsA("BodyGyro") then
			part:Destroy()
		end
	end
	carCopy.Parent = carsReplayFolder
	return carCopy
end

-- Função para destruir todas as cópias do carro no Workspace
local function destroyAllClones()
	for _, obj in pairs(Workspace:GetChildren()) do
		if obj.Name == "Clone" or obj.Name:match("^Clone%d+$") then
			obj:Destroy()
		end
	end
end

-- Função para atualizar a lista de replays no menu Replays
local function updateReplaysList()
	replaysScrollingFrame:ClearAllChildren()
	replaysScrollingFrameLayout.Parent = replaysScrollingFrame
	local yOffset = 0
	for i, replay in ipairs(savedReplays) do
		local replayButton = Instance.new("TextButton")
		replayButton.Size = UDim2.new(0, 360, 0, 60)
		replayButton.Position = UDim2.new(0, 0, 0, yOffset)
		replayButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
		replayButton.Text = string.format("Replay: %s\nCar: %s\nDuration: %s", replay.replayName, replay.carName, formatTime(replay.duration))
		replayButton.TextColor3 = Color3.fromRGB(200, 200, 200)
		replayButton.TextScaled = true
		replayButton.Font = Enum.Font.SourceSans
		replayButton.Parent = replaysScrollingFrame

		local replayButtonCorner = Instance.new("UICorner")
		replayButtonCorner.CornerRadius = UDim.new(0, 8)
		replayButtonCorner.Parent = replayButton

		local replayButtonStroke = Instance.new("UIStroke")
		replayButtonStroke.Color = Color3.fromRGB(88, 137, 192)
		replayButtonStroke.Thickness = 1
		replayButtonStroke.Parent = replayButton

		replayButton.MouseButton1Click:Connect(function()
			replayAllPartsActions(replay.recordings, replay.carModel)
		end)

		yOffset = yOffset + 70
	end
	replaysScrollingFrame.CanvasSize = UDim2.new(0, 0, 0, yOffset)
end

-- Função para reproduzir as gravações em todas as partes (ancorado)
local function replayAllPartsActions(recordingsToPlay, carModel)
	if #recordingsToPlay == 0 then
		replayButton.Text = "No Data!"
		task.wait(1)
		replayButton.Text = "Replay"
		return
	end

	local carCopy = duplicateCar(carModel)
	if not carCopy then
		replayButton.Text = "No Car!"
		task.wait(1)
		replayButton.Text = "Replay"
		return
	end

	local partsMap = {}
	local partIndex = {}
	for _, part in pairs(carCopy:GetDescendants()) do
		if part:IsA("BasePart") then
			local partName = part.Name
			partIndex[partName] = (partIndex[partName] or 0) + 1
			local uniqueId = getUniquePartId(part, partIndex[partName])
			partsMap[uniqueId] = part
		end
	end

	if next(partsMap) == nil then
		replayButton.Text = "No Parts!"
		task.wait(1)
		replayButton.Text = "Replay"
		carCopy:Destroy()
		return
	end

	local startReplayTime = tick()
	local index = 1

	replayConnection = RunService.Heartbeat:Connect(function()
		local currentTime = tick() - startReplayTime
		if index > #recordingsToPlay then
			if replayConnection then
				replayConnection:Disconnect()
			end
			return
		end

		while index < #recordingsToPlay and recordingsToPlay[index].time <= currentTime do
			index = index + 1
		end

		local prevFrame = recordingsToPlay[math.max(1, index - 1)]
		local nextFrame = recordingsToPlay[index] or prevFrame
		local t = (currentTime - prevFrame.time) / (nextFrame.time - prevFrame.time)
		t = math.clamp(t, 0, 1)

		for uniqueId, part in pairs(partsMap) do
			local prevCFrame = prevFrame.parts[uniqueId]
			local nextCFrame = nextFrame.parts[uniqueId]
			if prevCFrame and nextCFrame then
				local lerpedCFrame = prevCFrame:Lerp(nextCFrame, t)
				part.CFrame = lerpedCFrame
			end
		end
	end)
end

-- Conexão do botão principal
mainButton.MouseButton1Click:Connect(function()
	mainMenuFrame.Visible = not mainMenuFrame.Visible
	replayFrame.Visible = false
	replaysFrame.Visible = false
	savePopupFrame.Visible = false
end)

-- Conexão do botão Replay Menu
replayMenuButton.MouseButton1Click:Connect(function()
	mainMenuFrame.Visible = false
	replayFrame.Visible = true
	replaysFrame.Visible = false
	savePopupFrame.Visible = false
end)

-- Conexão do botão Replays Menu
replaysMenuButton.MouseButton1Click:Connect(function()
	mainMenuFrame.Visible = false
	replayFrame.Visible = false
	replaysFrame.Visible = true
	savePopupFrame.Visible = false
	updateReplaysList()
end)

-- Conexão do botão Play
playButton.MouseButton1Click:Connect(function()
	isRecording = not isRecording
	if isRecording then
		-- Iniciar gravação
		recordings = {}
		startTime = tick()
		elapsedTime = 0
		timeLabel.Text = "00:00:000"
		currentReplayCarModel = saveCarModel()
		if not currentReplayCarModel then
			playButton.Text = "No Car!"
			task.wait(1)
			playButton.Text = "Play"
			isRecording = false
			return
		end
		heartbeatConnection = RunService.Heartbeat:Connect(function()
			recordAllPartsActions()
			updateTimeLabel()
		end)
		playButton.Text = "Stop"
	else
		-- Parar gravação
		if heartbeatConnection then
			heartbeatConnection:Disconnect()
		end
		playButton.Text = "Play"
		if #recordings > 0 then
			savePopupFrame.Visible = true
		end
	end
end)

-- Conexão do botão Clear
clearButton.MouseButton1Click:Connect(function()
	recordings = {}
	elapsedTime = 0
	timeLabel.Text = "00:00:000"
	if isRecording then
		isRecording = false
		if heartbeatConnection then
			heartbeatConnection:Disconnect()
		end
		playButton.Text = "Play"
	end
	currentReplayCarModel = nil
	destroyAllClones()
end)

-- Conexão do botão Replay
replayButton.MouseButton1Click:Connect(function()
	if isRecording then
		replayButton.Text = "Stop Recording!"
		task.wait(1)
		replayButton.Text = "Replay"
		return
	end
	if currentReplayCarModel then
		replayAllPartsActions(recordings, currentReplayCarModel)
	end
end)

-- Conexão do botão Save
saveButton.MouseButton1Click:Connect(function()
	savePopupFrame.Visible = true
end)

-- Conexão do botão Confirm Save
confirmSaveButton.MouseButton1Click:Connect(function()
	local replayName = replayNameInput.Text ~= "" and replayNameInput.Text or "Unnamed Replay"
	local carName = carNameInput.Text ~= "" and carNameInput.Text or "Unnamed Car"
	if #recordings > 0 and currentReplayCarModel then
		table.insert(savedReplays, {
			replayName = replayName,
			carName = carName,
			duration = elapsedTime,
			recordings = recordings,
			carModel = currentReplayCarModel
		})
	end
	savePopupFrame.Visible = false
	replayNameInput.Text = "Replay Name"
	carNameInput.Text = "Car Name"
end)

-- Inicializar interface
updateReplaysList()
