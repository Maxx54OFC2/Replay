local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local Workspace = game:GetService("Workspace")
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

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

-- Criar Frame da Interface
local uiFrame = Instance.new("Frame")
uiFrame.Size = UDim2.new(0, 350, 0, 300)
uiFrame.Position = UDim2.new(0.1, 60, 0, 10)
uiFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
uiFrame.Visible = false
uiFrame.Active = true
uiFrame.Draggable = true
uiFrame.Parent = screenGui

local uiFrameCorner = Instance.new("UICorner")
uiFrameCorner.CornerRadius = UDim.new(0, 12)
uiFrameCorner.Parent = uiFrame

local uiFrameStroke = Instance.new("UIStroke")
uiFrameStroke.Color = Color3.fromRGB(88, 137, 192)
uiFrameStroke.Thickness = 1
uiFrameStroke.Parent = uiFrame

-- Título "Replay"
local titleLabel = Instance.new("TextLabel")
titleLabel.Size = UDim2.new(1, 0, 0, 30)
titleLabel.Position = UDim2.new(0, 0, 0, 5)
titleLabel.BackgroundTransparency = 1
titleLabel.Text = "Replay"
titleLabel.TextColor3 = Color3.fromRGB(200, 200, 200)
titleLabel.TextScaled = true
titleLabel.Font = Enum.Font.SourceSansBold
titleLabel.Parent = uiFrame

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
timeLabel.Parent = uiFrame

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
playButton.Parent = uiFrame

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
clearButton.Parent = uiFrame

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
replayButton.Parent = uiFrame

local replayButtonCorner = Instance.new("UICorner")
replayButtonCorner.CornerRadius = UDim.new(0, 8)
replayButtonCorner.Parent = replayButton

local replayButtonStroke = Instance.new("UIStroke")
replayButtonStroke.Color = Color3.fromRGB(255, 255, 255)
replayButtonStroke.Thickness = 1
replayButtonStroke.Parent = replayButton

-- Variáveis de controle
local isRecording = false
local recordings = {}
local startTime = 0
local elapsedTime = 0
local heartbeatConnection
local replayConnection
local wheelNames = {"FR", "FL", "RL", "RR"}

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

-- Função para encontrar o chassi (VehicleSeat)
local function getChassis(car)
	return car and car:FindFirstChild("VehicleSeat", true)
end

-- Função para gravar ações das rodas
local function recordWheelActions()
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

	local chassis = getChassis(car)
	if not chassis then
		playButton.Text = "No Chassis!"
		task.wait(1)
		playButton.Text = isRecording and "Stop" or "Play"
		isRecording = false
		if heartbeatConnection then
			heartbeatConnection:Disconnect()
		end
		return
	end

	local wheelsFolder = car:FindFirstChild("Wheels")
	if not wheelsFolder then
		playButton.Text = "No Wheels!"
		task.wait(1)
		playButton.Text = isRecording and "Stop" or "Play"
		isRecording = false
		if heartbeatConnection then
			heartbeatConnection:Disconnect()
		end
		return
	end

	local wheelData = {}
	local allWheelsFound = true
	for _, wheelName in ipairs(wheelNames) do
		local wheel = wheelsFolder:FindFirstChild(wheelName)
		if wheel then
			local constraint = wheel:FindFirstChildWhichIsA("CylindricalConstraint") or wheel:FindFirstChildWhichIsA("HingeConstraint")
			if constraint then
				-- Gravar CFrame relativo ao chassi
				local relativeCFrame = chassis.CFrame:ToObjectSpace(wheel.CFrame)
				wheelData[wheelName] = {
					relativeCFrame = relativeCFrame,
					angularVelocity = constraint.AngularVelocity
				}
			else
				allWheelsFound = false
				break
			end
		else
			allWheelsFound = false
			break
		end
	end

	if not allWheelsFound then
		playButton.Text = "Invalid Wheels!"
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
		wheelData = wheelData,
		chassisCFrame = chassis.CFrame -- Gravar CFrame do chassi
	})
end

-- Função para duplicar o carro
local function duplicateCar()
	local car = getPlayerCar()
	if not car then
		return nil
	end

	local carCopy = car:Clone()
	carCopy.Name = "ReplayCar"
	for _, part in pairs(carCopy:GetDescendants()) do
		if part:IsA("BasePart") then
			part.Anchored = false
			part.CanCollide = false -- Evita colisões
		elseif part:IsA("VehicleSeat") then
			part.Disabled = true -- Desativa controle
		elseif part:IsA("BodyVelocity") or part:IsA("BodyGyro") then
			part:Destroy() -- Remove controles de física
		end
	end
	carCopy.Parent = car.Parent
	return carCopy
end

-- Função para destruir a cópia do carro
local function destroyReplayCar()
	local carCollection = Workspace:FindFirstChild("CarCollection")
	if carCollection then
		local replayCar = carCollection:FindFirstChild("ReplayCar")
		if replayCar then
			replayCar:Destroy()
		end
	end
end

-- Função para reproduzir as gravações nas rodas
local function replayWheelActions()
	if #recordings == 0 then
		replayButton.Text = "No Data!"
		task.wait(1)
		replayButton.Text = "Replay"
		return
	end

	local carCopy = duplicateCar()
	if not carCopy then
		replayButton.Text = "No Car!"
		task.wait(1)
		replayButton.Text = "Replay"
		return
	end

	local chassis = getChassis(carCopy)
	if not chassis then
		replayButton.Text = "No Chassis!"
		task.wait(1)
		replayButton.Text = "Replay"
		carCopy:Destroy()
		return
	end

	local wheelsFolder = carCopy:FindFirstChild("Wheels")
	if not wheelsFolder then
		replayButton.Text = "No Wheels!"
		task.wait(1)
		replayButton.Text = "Replay"
		carCopy:Destroy()
		return
	end

	local wheels = {}
	local allWheelsFound = true
	for _, wheelName in ipairs(wheelNames) do
		local wheel = wheelsFolder:FindFirstChild(wheelName)
		if wheel then
			local constraint = wheel:FindFirstChildWhichIsA("CylindricalConstraint") or wheel:FindFirstChildWhichIsA("HingeConstraint")
			if constraint then
				wheels[wheelName] = { part = wheel, constraint = constraint }
			else
				allWheelsFound = false
				break
			end
		else
			allWheelsFound = false
			break
		end
	end

	if not allWheelsFound then
		replayButton.Text = "Invalid Wheels!"
		task.wait(1)
		replayButton.Text = "Replay"
		carCopy:Destroy()
		return
	end

	-- Ancorrar o chassi temporariamente
	chassis.Anchored = true

	-- Posicionar o chassi no CFrame inicial
	local initialChassisCFrame = recordings[1].chassisCFrame
	if initialChassisCFrame then
		chassis.CFrame = initialChassisCFrame
	end

	-- Posicionar as rodas no primeiro frame
	local firstFrame = recordings[1]
	for _, wheelName in ipairs(wheelNames) do
		local wheel = wheels[wheelName]
		local wheelData = firstFrame.wheelData[wheelName]
		if wheel and wheelData then
			wheel.part.CFrame = chassis.CFrame * wheelData.relativeCFrame
			wheel.constraint.AngularVelocity = 0 -- Inicializar com 0 para estabilidade
		end
	end

	-- Aguardar um frame para estabilizar
	task.wait()

	-- Liberar o chassi
	chassis.Anchored = false

	local startReplayTime = tick()
	local index = 1

	replayConnection = RunService.Heartbeat:Connect(function()
		local currentTime = tick() - startReplayTime
		if index > #recordings then
			-- Congelar o carro no final
			for _, part in pairs(carCopy:GetDescendants()) do
				if part:IsA("BasePart") then
					part.Anchored = true
				end
			end
			if replayConnection then
				replayConnection:Disconnect()
			end
			return
		end

		while index < #recordings and recordings[index].time <= currentTime do
			index = index + 1
		end

		local prevFrame = recordings[math.max(1, index - 1)]
		local nextFrame = recordings[index] or prevFrame
		local t = (currentTime - prevFrame.time) / (nextFrame.time - prevFrame.time)
		t = math.clamp(t, 0, 1)

		for _, wheelName in ipairs(wheelNames) do
			local wheel = wheels[wheelName]
			local prevData = prevFrame.wheelData[wheelName]
			local nextData = nextFrame.wheelData[wheelName]
			if prevData and nextData and wheel then
				-- Interpolar CFrame relativo e aplicar ao espaço mundial
				local lerpedRelativeCFrame = prevData.relativeCFrame:Lerp(nextData.relativeCFrame, t)
				local lerpedAngularVelocity = prevData.angularVelocity + (nextData.angularVelocity - prevData.angularVelocity) * t
				-- Limitar AngularVelocity para evitar picos
				lerpedAngularVelocity = math.clamp(lerpedAngularVelocity, -100, 100)
				wheel.part.CFrame = chassis.CFrame * lerpedRelativeCFrame
				wheel.constraint.AngularVelocity = lerpedAngularVelocity
			end
		end
	end)
end

-- Conexão do botão principal
mainButton.MouseButton1Click:Connect(function()
	uiFrame.Visible = not uiFrame.Visible
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
		heartbeatConnection = RunService.Heartbeat:Connect(function()
			recordWheelActions()
			updateTimeLabel()
		end)
		playButton.Text = "Stop"
	else
		-- Parar gravação
		if heartbeatConnection then
			heartbeatConnection:Disconnect()
		end
		playButton.Text = "Play"
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
	-- Destruir a cópia do carro
	destroyReplayCar()
end)

-- Conexão do botão Replay
replayButton.MouseButton1Click:Connect(function()
	if isRecording then
		replayButton.Text = "Stop Recording!"
		task.wait(1)
		replayButton.Text = "Replay"
		return
	end
	-- Destruir qualquer cópia existente antes de iniciar um novo replay
	destroyReplayCar()
	replayWheelActions()
end)
