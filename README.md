loadstring(game:HttpGet("https://raw.githubusercontent.com/Darkmoonxhubscript/DarkLibV2/refs/heads/main/Source.luau"))()

local Window = MakeWindow({Title = "luckystarz hub𒅒𒈔🤡🤡𒅒𒈔𒅒𒇫𒄆𒅒𒈔𒅒𒇫𒄆"})
--[[
Title ="DarkMoonHub Library" >> UI Title (String)
]]

AddMinimizeButton({Icon = "81310111804469"})
--[[
Icon = "Id" >> Button Image Id (String)
You Can Get Ids in:
https://github.com/Darkmoonxhubscript/DarkLibV2/blob/main/Icons.luau or Use Custom Icon Id
]]

-- ID do som a ser reproduzido quando o código for executado
local soundId = "rbxassetid://103211341252816"

-- Função para tocar o som
local function playSound()
    local sound = Instance.new("Sound")
    sound.SoundId = soundId
    sound.Parent = game.Workspace -- Coloque no Workspace para garantir que seja ouvido
    sound:Play()
end

-- Tocar o som assim que o script for executado
playSound()

local Tab1 = NewTab({Name = "main", Icon = "IconName"})
--[[
Name = "TabName" >> UI Button TabName (String)
Icon = "IconName" >> Tab Icon, No Need Put Id, You can get Icons In:.
https://github.com/Darkmoonxhubscript/DarkLibV2/blob/main/Icons.luau
]]

local Button1 = AddButton(Tab1, {
  Name = "mola speed",
  Callback = function()local player = game.Players.LocalPlayer
        local backpack = player:WaitForChild("Backpack")
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:WaitForChild("Humanoid")
        local originalWalkSpeed = humanoid.WalkSpeed

        local h = Instance.new("Model", game:GetService("Lighting"))

        local i = Instance.new("Tool")
        i.Name = "SPEEDTOOL"
        i.Parent = h
        i.Grip = CFrame.new(0, 0, 0, 0, 1, 0, 0, 0, 1, 1, 0, 0)
        i.GripForward = Vector3.new(0, -1, 0)
        i.GripRight = Vector3.new(0, 0, 1)
        i.GripUp = Vector3.new(1, 0, 0)
        i.TextureId = "rbxassetid://106331933297015"

        local j = Instance.new("Part")
        j.Name = "Handle"
        j.Parent = i
        j.Size = Vector3.new(1, 1.2, 1)
        j.Color = Color3.new(0.0666667, 0.0666667, 0.0666667)
        j.Transparency = 1
        j.Anchored = false
        j.CanCollide = false

        local function onEquipped()
            humanoid.WalkSpeed = 100

            local args = {
                [1] = "wear",
                [2] = 18385684081
            }
            local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
            if updateAvatarEvent then
                updateAvatarEvent:FireServer(unpack(args))
            end
        end

        local function onUnequipped()
            humanoid.WalkSpeed = originalWalkSpeed

            local args = {
                [1] = "remove",
                [2] = 18385684081
            }
            local updateAvatarEvent = game:GetService("ReplicatedStorage").RE:FindFirstChild("1Updat1eAvata1r")
            if updateAvatarEvent then
                updateAvatarEvent:FireServer(unpack(args))
            end
        end

        i.Equipped:Connect(onEquipped)
        i.Unequipped:Connect(onUnequipped)

        i.Parent = backpack

        print("Tool speed add")
  print("Clicked")
  end
})
--[[
Name = "Text" >> Button Text (String)
Callback = function(Value) -button press function
-- function here
end --end function
]]

local Button1 = AddButton(Tab1, {
  Name = "super rings v6",
  Callback = function()-- The tags get stealed and i will not leak it
local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local UserInputService = game:GetService("UserInputService")
local SoundService = game:GetService("SoundService")
local StarterGui = game:GetService("StarterGui")
local HttpService = game:GetService("HttpService")

local LocalPlayer = Players.LocalPlayer

-- Sound Effects
local function playSound(soundId)
    local sound = Instance.new("Sound")
    sound.SoundId = "rbxassetid://" .. soundId
    sound.Parent = SoundService
    sound:Play()
    sound.Ended:Connect(function()
        sound:Destroy()
    end)
end

-- Play initial sound
playSound("2865227271")

-- GUI Creation
local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "SuperRingPartsGUI"
ScreenGui.ResetOnSpawn = false
ScreenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")

local MainFrame = Instance.new("Frame")
MainFrame.Size = UDim2.new(0, 300, 0, 500)
MainFrame.Position = UDim2.new(0.5, -150, 0.5, -250)
MainFrame.BorderSizePixel = 0
MainFrame.Parent = ScreenGui

-- Make the GUI round
local UICorner = Instance.new("UICorner")
UICorner.CornerRadius = UDim.new(0, 20)
UICorner.Parent = MainFrame

local Title = Instance.new("TextLabel")
Title.Size = UDim2.new(1, 0, 0, 40)
Title.Position = UDim2.new(0, 0, 0, 0)
Title.Text = "Super Ring Parts V6 by lukas"
Title.TextColor3 = Color3.fromRGB(0, 0, 0)
Title.BackgroundColor3 = Color3.fromRGB(0, 204, 204)
Title.Font = Enum.Font.Fondamento
Title.TextSize = 22
Title.Parent = MainFrame

-- Round the title
local TitleCorner = Instance.new("UICorner")
TitleCorner.CornerRadius = UDim.new(0, 20)
TitleCorner.Parent = Title

local ToggleButton = Instance.new("TextButton")
ToggleButton.Size = UDim2.new(0.8, 0, 0, 40)
ToggleButton.Position = UDim2.new(0.1, 0, 0.1, 0)
ToggleButton.Text = "Ring Off"
ToggleButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
ToggleButton.TextColor3 = Color3.fromRGB(0, 0, 0)
ToggleButton.Font = Enum.Font.Fondamento
ToggleButton.TextSize = 18
ToggleButton.Parent = MainFrame

-- Round the toggle button
local ToggleCorner = Instance.new("UICorner")
ToggleCorner.CornerRadius = UDim.new(0, 10)
ToggleCorner.Parent = ToggleButton

-- Configuration table
local config = {
    radius = 50,
    height = 100,
    rotationSpeed = 10,
    attractionStrength = 1000,
}

-- Save and load functions
local function saveConfig()
    local configStr = HttpService:JSONEncode(config)
    writefile("SuperRingPartsConfig.txt", configStr)
end

local function loadConfig()
    if isfile("SuperRingPartsConfig.txt") then
        local configStr = readfile("SuperRingPartsConfig.txt")
        config = HttpService:JSONDecode(configStr)
    end
end

loadConfig()

-- Function to create control buttons and textboxes
local function createControl(name, positionY, color, labelText, defaultValue, callback)
    local DecreaseButton = Instance.new("TextButton")
    DecreaseButton.Size = UDim2.new(0.2, 0, 0, 40)
    DecreaseButton.Position = UDim2.new(0.1, 0, positionY, 0)
    DecreaseButton.Text = "-"
    DecreaseButton.BackgroundColor3 = color
    DecreaseButton.TextColor3 = Color3.fromRGB(0, 0, 0)
    DecreaseButton.Font = Enum.Font.Fondamento
    DecreaseButton.TextSize = 18
    DecreaseButton.Parent = MainFrame

    local IncreaseButton = Instance.new("TextButton")
    IncreaseButton.Size = UDim2.new(0.2, 0, 0, 40)
    IncreaseButton.Position = UDim2.new(0.7, 0, positionY, 0)
    IncreaseButton.Text = "+"
    IncreaseButton.BackgroundColor3 = color
    IncreaseButton.TextColor3 = Color3.fromRGB(0, 0, 0)
    IncreaseButton.Font = Enum.Font.Fondamento
    IncreaseButton.TextSize = 18
    IncreaseButton.Parent = MainFrame

    local Display = Instance.new("TextLabel")
    Display.Size = UDim2.new(0.4, 0, 0, 40)
    Display.Position = UDim2.new(0.3, 0, positionY, 0)
    Display.Text = labelText .. ": " .. defaultValue
    Display.BackgroundColor3 = Color3.fromRGB(255, 153, 51)
    Display.TextColor3 = Color3.fromRGB(0, 0, 0)
    Display.Font = Enum.Font.Fondamento
    Display.TextSize = 18
    Display.Parent = MainFrame

    -- Add TextBox for input
    local TextBox = Instance.new("TextBox")
    TextBox.Size = UDim2.new(0.8, 0, 0, 35)
    TextBox.Position = UDim2.new(0.1, 0, positionY + 0.1, 0)
    TextBox.PlaceholderText = "Enter " .. labelText
    TextBox.BackgroundColor3 = Color3.fromRGB(0, 0, 255)
    TextBox.TextColor3 = Color3.fromRGB(0, 0, 0)
    TextBox.Font = Enum.Font.Fondamento
    TextBox.TextSize = 18
    TextBox.Parent = MainFrame

    local TextBoxCorner = Instance.new("UICorner")
    TextBoxCorner.CornerRadius = UDim.new(0, 10)
    TextBoxCorner.Parent = TextBox

    DecreaseButton.MouseButton1Click:Connect(function()
        local value = tonumber(Display.Text:match("%d+"))
        value = math.max(0, value - 10)
        Display.Text = labelText .. ": " .. value
        callback(value)
        playSound("12221967")
        saveConfig()
    end)

    IncreaseButton.MouseButton1Click:Connect(function()
        local value = tonumber(Display.Text:match("%d+"))
        value = math.min(10000, value + 10)
        Display.Text = labelText .. ": " .. value
        callback(value)
        playSound("12221967")
        saveConfig()
    end)

    TextBox.FocusLost:Connect(function(enterPressed)
        if enterPressed then
            local newValue = tonumber(TextBox.Text)
            if newValue then
                newValue = math.clamp(newValue, 0, 10000)
                Display.Text = labelText .. ": " .. newValue
                TextBox.Text = ""
                callback(newValue)
                playSound("12221967")
                saveConfig()
            else
                TextBox.Text = ""
            end
        end
    end)
end

createControl("Radius", 0.2, Color3.fromRGB(153, 153, 0), "Radius", config.radius, function(value)
    config.radius = value
    saveConfig()
end)

createControl("Height", 0.4, Color3.fromRGB(153, 0, 153), "Height", config.height, function(value)
    config.height = value
    saveConfig()
end)

createControl("RotationSpeed", 0.6, Color3.fromRGB(0, 153, 153), "Rotation Speed", config.rotationSpeed, function(value)
    config.rotationSpeed = value
    saveConfig()
end)

createControl("AttractionStrength", 0.8, Color3.fromRGB(153, 0, 0), "Attraction Strength", config.attractionStrength, function(value)
    config.attractionStrength = value
    saveConfig()
end)

-- Add minimize button
local MinimizeButton = Instance.new("TextButton")
MinimizeButton.Size = UDim2.new(0, 30, 0, 30)
MinimizeButton.Position = UDim2.new(1, -35, 0, 5)
MinimizeButton.Text = "-"
MinimizeButton.BackgroundColor3 = Color3.fromRGB(255, 255, 0)
MinimizeButton.TextColor3 = Color3.fromRGB(0, 0, 0)
MinimizeButton.Font = Enum.Font.Fondamento
MinimizeButton.TextSize = 15
MinimizeButton.Parent = MainFrame

-- Round the minimize button
local MinimizeCorner = Instance.new("UICorner")
MinimizeCorner.CornerRadius = UDim.new(0, 15)
MinimizeCorner.Parent = MinimizeButton

-- Minimize functionality
local minimized = false
MinimizeButton.MouseButton1Click:Connect(function()
    minimized = not minimized
    if minimized then
        MainFrame:TweenSize(UDim2.new(0, 300, 0, 40), "Out", "Quad", 0.3, true)
        MinimizeButton.Text = "+"
        for _, child in pairs(MainFrame:GetChildren()) do
            if child:IsA("GuiObject") and child ~= Title and child ~= MinimizeButton then
                child.Visible = false
            end
        end
    else
        MainFrame:TweenSize(UDim2.new(0, 300, 0, 500), "Out", "Quad", 0.3, true)
        MinimizeButton.Text = "-"
        for _, child in pairs(MainFrame:GetChildren()) do
            if child:IsA("GuiObject") then
                child.Visible = true
            end
        end
    end
    playSound("12221967")
end)

-- Make GUI draggable
local dragging
local dragInput
local dragStart
local startPos

local function update(input)
    local delta = input.Position - dragStart
    MainFrame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
end

MainFrame.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        dragging = true
        dragStart = input.Position
        startPos = MainFrame.Position
        
        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

MainFrame.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
        dragInput = input
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if input == dragInput and dragging then
        update(input)
    end
end)

-- Ring Parts Claim
local Workspace = game:GetService("Workspace")

local character = LocalPlayer.Character or LocalPlayer.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

local Folder = Instance.new("Folder", Workspace)
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1

if not getgenv().Network then
    getgenv().Network = {
        BaseParts = {},
        Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
    }

    Network.RetainPart = function(Part)
        if typeof(Part) == "Instance" and Part:IsA("BasePart") and Part:IsDescendantOf(Workspace) then
            table.insert(Network.BaseParts, Part)
            Part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
            Part.CanCollide = false
        end
    end

    local function EnablePartControl()
        LocalPlayer.ReplicationFocus = Workspace
        RunService.Heartbeat:Connect(function()
            sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
            for _, Part in pairs(Network.BaseParts) do
                if Part:IsDescendantOf(Workspace) then
                    Part.Velocity = Network.Velocity
                end
            end
        end)
    end

    EnablePartControl()
end

local function ForcePart(v)
    if v:IsA("Part") and not v.Anchored and not v.Parent:FindFirstChild("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
        for _, x in next, v:GetChildren() do
            if x:IsA("BodyAngularVelocity") or x:IsA("BodyForce") or x:IsA("BodyGyro") or x:IsA("BodyPosition") or x:IsA("BodyThrust") or x:IsA("BodyVelocity") or x:IsA("RocketPropulsion") then
                x:Destroy()
            end
        end
        if v:FindFirstChild("Attachment") then
            v:FindFirstChild("Attachment"):Destroy()
        end
        if v:FindFirstChild("AlignPosition") then
            v:FindFirstChild("AlignPosition"):Destroy()
        end
        if v:FindFirstChild("Torque") then
            v:FindFirstChild("Torque"):Destroy()
        end
        v.CanCollide = false
        local Torque = Instance.new("Torque", v)
        Torque.Torque = Vector3.new(100000, 100000, 100000)
        local AlignPosition = Instance.new("AlignPosition", v)
        local Attachment2 = Instance.new("Attachment", v)
        Torque.Attachment0 = Attachment2
        AlignPosition.MaxForce = 9999999999999999999999999999999
        AlignPosition.MaxVelocity = math.huge
        AlignPosition.Responsiveness = 200
        AlignPosition.Attachment0 = Attachment2
        AlignPosition.Attachment1 = Attachment1
    end
end

-- Edits
local ringPartsEnabled = false

local function RetainPart(Part)
    if Part:IsA("BasePart") and not Part.Anchored and Part:IsDescendantOf(workspace) then
        if Part.Parent == LocalPlayer.Character or Part:IsDescendantOf(LocalPlayer.Character) then
            return false
        end

        Part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
        Part.CanCollide = false
        return true
    end
    return false
end

local parts = {}
local function addPart(part)
    if RetainPart(part) then
        if not table.find(parts, part) then
            table.insert(parts, part)
        end
    end
end

local function removePart(part)
    local index = table.find(parts, part)
    if index then
        table.remove(parts, index)
    end
end

for _, part in pairs(workspace:GetDescendants()) do
    addPart(part)
end

workspace.DescendantAdded:Connect(addPart)
workspace.DescendantRemoving:Connect(removePart)

RunService.Heartbeat:Connect(function()
    if not ringPartsEnabled then return end
    
    local humanoidRootPart = LocalPlayer.Character and LocalPlayer.Character:FindFirstChild("HumanoidRootPart")
    if humanoidRootPart then
        local tornadoCenter = humanoidRootPart.Position
        for _, part in pairs(parts) do
            if part.Parent and not part.Anchored then
                local pos = part.Position
                local distance = (Vector3.new(pos.X, tornadoCenter.Y, pos.Z) - tornadoCenter).Magnitude
                local angle = math.atan2(pos.Z - tornadoCenter.Z, pos.X - tornadoCenter.X)
                local newAngle = angle + math.rad(config.rotationSpeed)
                local targetPos = Vector3.new(
                    tornadoCenter.X + math.cos(newAngle) * math.min(config.radius, distance),
                    tornadoCenter.Y + (config.height * (math.abs(math.sin((pos.Y - tornadoCenter.Y) / config.height)))),
                    tornadoCenter.Z + math.sin(newAngle) * math.min(config.radius, distance)
                )
                local directionToTarget = (targetPos - part.Position).unit
                part.Velocity = directionToTarget * config.attractionStrength
            end
        end
    end
end)

-- Button functionality
ToggleButton.MouseButton1Click:Connect(function()
    ringPartsEnabled = not ringPartsEnabled
    ToggleButton.Text = ringPartsEnabled and "Tornado On" or "Tornado Off"
    ToggleButton.BackgroundColor3 = ringPartsEnabled and Color3.fromRGB(50, 205, 50) or Color3.fromRGB(160, 82, 45)
    playSound("12221967")
end)

-- Get player thumbnail
local userId = Players:GetUserIdFromNameAsync("Robloxlukasgames")
local thumbType = Enum.ThumbnailType.HeadShot
local thumbSize = Enum.ThumbnailSize.Size420x420
local content, isReady = Players:GetUserThumbnailAsync(userId, thumbType, thumbSize)

StarterGui:SetCore("SendNotification", {
    Title = "Hey",
    Text = "Enjoy the Script!",
    Icon = content,
    Duration = 5
})

StarterGui:SetCore("SendNotification", {
    Title = "TIPS",
    Text = "Click Textbox To edit Any of them",
    Icon = content,
    Duration = 5
})

StarterGui:SetCore("SendNotification", {
    Title = "Credits",
    Text = "On scriptblox!",
    Icon = content,
    Duration = 5
})


-- Rainbow Background Effect
local hue = 0
RunService.Heartbeat:Connect(function()
    hue = (hue + 0.01) % 1
    MainFrame.BackgroundColor3 = Color3.fromHSV(hue, 1, 1)
end)

-- Rainbow TextLabel
local textHue = 0
RunService.Heartbeat:Connect(function()
    textHue = (textHue + 0.01) % 1
    Title.TextColor3 = Color3.fromHSV(textHue, 1, 1)
end)


-- fly gui

local TextButton1 = Instance.new("TextButton") 
TextButton1.Parent = MainFrame
TextButton1.Name = "Fly gui"
TextButton1.BackgroundColor3 = Color3.fromRGB(0,0,255)
TextButton1.BackgroundTransparency = 0
TextButton1.BorderSizePixel = 1
TextButton1.BorderColor3 = Color3.fromRGB(17,17,17)
TextButton1.Position = UDim2.new(1,0,1)
TextButton1.Size = UDim2.new(0.08,0,0.1)
TextButton1.Font = Enum.Font.Legacy
TextButton1.TextColor3 = Color3.fromRGB(242,243,243)
TextButton1.Text = "Fly Gui"
TextButton1.TextSize = 18
TextButton1.TextScaled = true
TextButton1.TextWrapped = true
TextButton1.Visible = true
TextButton1.Active = true

TextButton1.MouseButton1Click:Connect(function() 
loadstring(game:HttpGet('https://pastebin.com/raw/YSL3xKYU'))()
end)

-- no fall damage
local TextButton1 = Instance.new("TextButton") 
TextButton1.Parent = MainFrame
TextButton1.Name = "no fall damage"
TextButton1.BackgroundColor3 = Color3.fromRGB(255,0,0)
TextButton1.BackgroundTransparency = 0
TextButton1.BorderSizePixel = 1
TextButton1.BorderColor3 = Color3.fromRGB(17,17,17)
TextButton1.Position = UDim2.new(0.9,0,1)
TextButton1.Size = UDim2.new(0.08,0,0.1)
TextButton1.Font = Enum.Font.Legacy
TextButton1.TextColor3 = Color3.fromRGB(242,243,243)
TextButton1.Text = "No fall Damage"
TextButton1.TextSize = 18
TextButton1.TextScaled = true
TextButton1.TextWrapped = true
TextButton1.Visible = true
TextButton1.Active = true

TextButton1.MouseButton1Click:Connect(function() 
-- No Fall Damage by Pio (Discord: piomanly or ID: 311397526399877122) --
local runsvc = game:GetService("RunService")
local heartbeat = runsvc.Heartbeat
local rstepped = runsvc.RenderStepped

local lp = game.Players.LocalPlayer

local novel = Vector3.zero

local function nofalldamage(chr)
    local root = chr:WaitForChild("HumanoidRootPart")
    
    if root then
        local con
        con = heartbeat:Connect(function()
            if not root.Parent then
                con:Disconnect()
            end
            
            local oldvel = root.AssemblyLinearVelocity
            root.AssemblyLinearVelocity = novel
            
            rstepped:Wait()
            root.AssemblyLinearVelocity = oldvel
        end)
    end
end

nofalldamage(lp.Character)
    lp.CharacterAdded:Connect(nofalldamage)
end)

-- noclip
local TextButton1 = Instance.new("TextButton") 
TextButton1.Parent = MainFrame
TextButton1.Name = "noclip"
TextButton1.BackgroundColor3 = Color3.fromRGB(0,0,0)
TextButton1.BackgroundTransparency = 0
TextButton1.BorderSizePixel = 1
TextButton1.BorderColor3 = Color3.fromRGB(17,17,17)
TextButton1.Position = UDim2.new(0.8,0,1)
TextButton1.Size = UDim2.new(0.08,0,0.1)
TextButton1.Font = Enum.Font.Legacy
TextButton1.TextColor3 = Color3.fromRGB(242,243,243)
TextButton1.Text = "Noclip"
TextButton1.TextSize = 18
TextButton1.TextScaled = true
TextButton1.TextWrapped = true
TextButton1.Visible = true
TextButton1.Active = true

TextButton1.MouseButton1Click:Connect(function() 
local Noclip = nil
local Clip = nil

function noclip()
	Clip = false
	local function Nocl()
		if Clip == false and game.Players.LocalPlayer.Character ~= nil then
			for _,v in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
				if v:IsA('BasePart') and v.CanCollide and v.Name ~= floatName then
					v.CanCollide = false
				end
			end
		end
		wait(0.21) -- basic optimization
	end
	Noclip = game:GetService('RunService').Stepped:Connect(Nocl)
end

function clip()
	if Noclip then Noclip:Disconnect() end
	Clip = true
end

noclip() -- to toggle noclip() and clip()
end)

-- Inf jump

local TextButton1 = Instance.new("TextButton") 
TextButton1.Parent = MainFrame
TextButton1.Name = "Inf jump"
TextButton1.BackgroundColor3 = Color3.fromRGB(0,255,0)
TextButton1.BackgroundTransparency = 0
TextButton1.BorderSizePixel = 1
TextButton1.BorderColor3 = Color3.fromRGB(17,17,17)
TextButton1.Position = UDim2.new(0.7,0,1)
TextButton1.Size = UDim2.new(0.08,0,0.1)
TextButton1.Font = Enum.Font.Legacy
TextButton1.TextColor3 = Color3.fromRGB(242,243,243)
TextButton1.Text = "Inf jump"
TextButton1.TextSize = 18
TextButton1.TextScaled = true
TextButton1.TextWrapped = true
TextButton1.Visible = true
TextButton1.Active = true

TextButton1.MouseButton1Click:Connect(function() 
local InfiniteJumpEnabled = true game:GetService("UserInputService").JumpRequest:connect(function() 	if InfiniteJumpEnabled then 		game:GetService"Players".LocalPlayer.Character:FindFirstChildOfClass'Humanoid':ChangeState("Jumping") 	end end)
end)

-- Inf yield

local TextButton1 = Instance.new("TextButton") 
TextButton1.Parent = MainFrame
TextButton1.Name = "Inf yield"
TextButton1.BackgroundColor3 = Color3.fromRGB(0,255,255)
TextButton1.BackgroundTransparency = 0
TextButton1.BorderSizePixel = 1
TextButton1.BorderColor3 = Color3.fromRGB(17,17,17)
TextButton1.Position = UDim2.new(0.6,0,1)
TextButton1.Size = UDim2.new(0.08,0,0.1)
TextButton1.Font = Enum.Font.Legacy
TextButton1.TextColor3 = Color3.fromRGB(242,243,243)
TextButton1.Text = "Inf yield"
TextButton1.TextSize = 18
TextButton1.TextScaled = true
TextButton1.TextWrapped = true
TextButton1.Visible = true
TextButton1.Active = true

TextButton1.MouseButton1Click:Connect(function() 
loadstring(game:HttpGet('https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source'))()
end)

-- nameless admin

local TextButton1 = Instance.new("TextButton") 
TextButton1.Parent = MainFrame
TextButton1.Name = "nameless admin"
TextButton1.BackgroundColor3 = Color3.fromRGB(0,0,0)
TextButton1.BackgroundTransparency = 0
TextButton1.BorderSizePixel = 1
TextButton1.BorderColor3 = Color3.fromRGB(17,17,17)
TextButton1.Position = UDim2.new(0.5,0,1)
TextButton1.Size = UDim2.new(0.08,0,0.1)
TextButton1.Font = Enum.Font.Legacy
TextButton1.TextColor3 = Color3.fromRGB(242,243,243)
TextButton1.Text = "NAMELESS"
TextButton1.TextSize = 18
TextButton1.TextScaled = true
TextButton1.TextWrapped = true
TextButton1.Visible = true
TextButton1.Active = true

TextButton1.MouseButton1Click:Connect(function() 
loadstring(game:HttpGet("https://scriptblox.com/raw/Universal-Script-Nameless-Admin-FE-11243"))()
end)

-- fps

local TextButton1 = Instance.new("TextButton") 
TextButton1.Parent = MainFrame
TextButton1.Name = "FPS"
TextButton1.BackgroundColor3 = Color3.fromRGB(0,0,0)
TextButton1.BackgroundTransparency = 0
TextButton1.BorderSizePixel = 1
TextButton1.BorderColor3 = Color3.fromRGB(17,17,17)
TextButton1.Position = UDim2.new(0.4,0,1)
TextButton1.Size = UDim2.new(0.08,0,0.1)
TextButton1.Font = Enum.Font.Legacy
TextButton1.TextColor3 = Color3.fromRGB(242,243,243)
TextButton1.Text = "FPS"
TextButton1.TextSize = 18
TextButton1.TextScaled = true
TextButton1.TextWrapped = true
TextButton1.Visible = true
TextButton1.Active = true

TextButton1.MouseButton1Click:Connect(function() 
loadstring(game:HttpGet("https://pastebin.com/raw/ySHJdZpb",true))()
end)
-- Just that enjoy skidding this lol
  print("Clicked")
  end
})
--[[
Name = "Text" >> Button Text (String)
Callback = function(Value) -button press function
-- function here
end --end function
]]

local Button1 = AddButton(Tab1, {
  Name = "sistema de fala seila",
  Callback = function()local function createPixelSpeechBubble(player, text, typingSpeed, displayTime)
    -- Criação da BillboardGui
    local billboardGui = Instance.new("BillboardGui")
    billboardGui.Adornee = player.Character:FindFirstChild("Head")
    billboardGui.Size = UDim2.new(8, 0, 3, 0) -- Aumentando mais a largura do balão
    billboardGui.StudsOffset = Vector3.new(0, 3, 0)
    billboardGui.Parent = player.Character
    billboardGui.AlwaysOnTop = true

    -- Criação do Frame de Fundo
    local frame = Instance.new("Frame")
    frame.Size = UDim2.new(1, 0, 1, 0)
    frame.BackgroundTransparency = 0
    frame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    frame.BorderColor3 = Color3.fromRGB(255, 255, 255)
    frame.BorderSizePixel = 3
    frame.Parent = billboardGui

    -- Criação do ImageLabel para a Foto Pixelada do Jogador
    local imageLabel = Instance.new("ImageLabel")
    imageLabel.Size = UDim2.new(0.3, 0, 0.9, 0) -- Mantendo a imagem proporcional
    imageLabel.Position = UDim2.new(0.05, 0, 0.05, 0)
    imageLabel.BackgroundTransparency = 1
    imageLabel.Image = "https://www.roblox.com/headshot-thumbnail/image?userId=" .. player.UserId .. "&width=150&height=150&format=png"
    imageLabel.Parent = frame

    -- Criação do TextLabel com Fonte Pixelada
    local textLabel = Instance.new("TextLabel")
    textLabel.Size = UDim2.new(0.6, 0, 0.9, 0) -- Aumentando a largura do texto ainda mais
    textLabel.Position = UDim2.new(0.35, 0, 0.05, 0)
    textLabel.BackgroundTransparency = 1
    textLabel.Text = ""
    textLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
    textLabel.Font = Enum.Font.Arcade -- Fonte pixelada
    textLabel.TextScaled = true
    textLabel.TextWrapped = true
    textLabel.Parent = frame

    -- Função para o efeito de digitação
    local function typeEffect()
        local length = string.len(text)
        for i = 1, length do
            textLabel.Text = string.sub(text, 1, i)
            wait(typingSpeed)
        end
    end

    -- Função para remover o balão após o tempo especificado
    local function removeBubbleAfterTime()
        wait(displayTime)
        billboardGui:Destroy()
    end

    -- Iniciar efeito de digitação
    typeEffect()
    -- Iniciar temporizador para remover o balão
    spawn(removeBubbleAfterTime)
end

-- Exemplo de uso
createPixelSpeechBubble(game.Players.LocalPlayer, "Hello, this is a pixel-style message that should fit without pushing the text down!", 0.05, 5) -- 5 segundos de exibição
  print("Clicked")
  end
})
--[[
Name = "Text" >> Button Text (String)
Callback = function(Value) -button press function
-- function here
end --end function
]]

local Button1 = AddButton(Tab1, {
  Name = "hitbox",
  Callback = function()-- Gui to Lua
-- Version: 3.2

-- Instances:

local Close = Instance.new("TextButton")
local Open2 = Instance.new("ScreenGui")
local Open = Instance.new("TextButton")
local FightingGui = Instance.new("ScreenGui")
local main = Instance.new("Frame")
local Cre = Instance.new("TextLabel")
local HitBox = Instance.new("TextBox")
local Red = Instance.new("TextBox")
local Green = Instance.new("TextBox")
local Blue = Instance.new("TextBox")
local TextLabel = Instance.new("TextLabel")

--Properties:

FightingGui.Name = "FightingGui"
FightingGui.Parent = game.CoreGui
FightingGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling


Open2.Name = "Tools"
Open2.Parent = game.CoreGui
Open2.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Open.Name = "Open"
Open.Parent = Open2
Open.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
Open.Position = UDim2.new(0, 0, 0.451871663, 0)
Open.Size = UDim2.new(0, 78, 0, 50)
Open.Font = Enum.Font.SourceSans
Open.Text = "Open"
Open.TextColor3 = Color3.fromRGB(250, 0, 0)
Open.TextScaled = true
Open.TextSize = 14.000
Open.TextWrapped = true
Open.MouseButton1Down:Connect(function()
 FightingGui.Enabled = true
end)

Close.Name = "Close"
Close.Parent = main
Close.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
Close.Position = UDim2.new(1, 0, -0.226244345, 0)
Close.Size = UDim2.new(0, 60, 0, 50)
Close.Font = Enum.Font.SourceSans
Close.Text = "X"
Close.TextColor3 = Color3.fromRGB(0, 0, 0)
Close.TextScaled = true
Close.TextSize = 14.000
Close.TextWrapped = true
Close.MouseButton1Down:Connect(function()
 FightingGui.Enabled = false
end)

main.Parent = FightingGui
main.Active = true
main.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
main.Position = UDim2.new(0.073011741, 0, 0.237333342, 0)
main.Size = UDim2.new(0, 273, 0, 221)
main.Draggable = true

Cre.Name = "Cre"
Cre.Parent = main
Cre.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
Cre.Position = UDim2.new(0, 0, -0.226244345, 0)
Cre.Size = UDim2.new(0, 273, 0, 50)
Cre.Font = Enum.Font.SourceSans
Cre.Text = "Script made by KIWI HUB TEAM☄️"
Cre.TextColor3 = Color3.fromRGB(0, 0, 0)
Cre.TextScaled = true
Cre.TextSize = 14.000
Cre.TextWrapped = true

HitBox.Name = "HitBox"
HitBox.Parent = main
HitBox.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
HitBox.Position = UDim2.new(0.0586080588, 0, 0.0995475128, 0)
HitBox.Size = UDim2.new(0, 65, 0, 50)
HitBox.Font = Enum.Font.SourceSans
HitBox.PlaceholderColor3 = Color3.fromRGB(0, 0, 0)
HitBox.PlaceholderText = "Hitbox"
HitBox.Text = ""
HitBox.TextColor3 = Color3.fromRGB(0, 0, 0)
HitBox.TextScaled = true
HitBox.TextSize = 14.000
HitBox.TextWrapped = true

Red.Name = "Red"
Red.Parent = main
Red.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
Red.Position = UDim2.new(0.485832304, 0, 0.0995475128, 0)
Red.Size = UDim2.new(0, 37, 0, 31)
Red.Font = Enum.Font.SourceSans
Red.PlaceholderColor3 = Color3.fromRGB(0, 0, 0)
Red.PlaceholderText = "Red"
Red.Text = ""
Red.TextColor3 = Color3.fromRGB(0, 0, 0)
Red.TextSize = 14.000

Green.Name = "Green"
Green.Parent = main
Green.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
Green.Position = UDim2.new(0.665319502, 0, 0.0995475128, 0)
Green.Size = UDim2.new(0, 37, 0, 31)
Green.Font = Enum.Font.SourceSans
Green.PlaceholderColor3 = Color3.fromRGB(0, 0, 0)
Green.PlaceholderText = "Green"
Green.Text = ""
Green.TextColor3 = Color3.fromRGB(0, 0, 0)
Green.TextSize = 14.000

TextLabel.Parent = main
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
TextLabel.Position = UDim2.new(0.47118023, 0, 0.325791866, 0)
TextLabel.Size = UDim2.new(0, 140, 0, 37)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "Colors"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextScaled = true
TextLabel.TextSize = 14.000
TextLabel.TextWrapped = true

Blue.Name = "Blue"
Blue.Parent = main
Blue.BackgroundColor3 = Color3.fromRGB(0, 0, 255)
Blue.Position = UDim2.new(0.837480664, 0, 0.0995475128, 0)
Blue.Size = UDim2.new(0, 37, 0, 31)
Blue.Font = Enum.Font.SourceSans
Blue.PlaceholderColor3 = Color3.fromRGB(0, 0, 0)
Blue.PlaceholderText = "Blue"
Blue.Text = ""
Blue.TextColor3 = Color3.fromRGB(0, 0, 0)
Blue.TextSize = 14.000
game:GetService('RunService').RenderStepped:connect(function()
 for i,v in next, game:GetService('Players'):GetPlayers() do
  if v.Name ~= game:GetService('Players').LocalPlayer.Name then
   v.Character.HumanoidRootPart.Size = Vector3.new(HitBox.Text,HitBox.Text,HitBox.Text)
   v.Character.HumanoidRootPart.Transparency = 0.8
   v.Character.HumanoidRootPart.Color = Color3.new(Red.Text,Green.Text,Blue.Text)
   v.Character.HumanoidRootPart.Material = "Neon"
   v.Character.HumanoidRootPart.CanCollide = false
  end
 end
end)
  print("Clicked")
  end
})
--[[
Name = "Text" >> Button Text (String)
Callback = function(Value) -button press function
-- function here
end --end function
]]

local Button1 = AddButton(Tab1, {
  Name = "team dude",
  Callback = function()-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local ImageLabel = Instance.new("ImageLabel")
local Dude09123skybox = Instance.new("TextButton")
local Dude09123theme = Instance.new("TextButton")
local decalspam = Instance.new("TextButton")
local teamcamerontheme = Instance.new("TextButton")
local disco = Instance.new("TextButton")
local hint = Instance.new("TextButton")
local TextLabel_2 = Instance.new("TextLabel")

--Properties:

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Frame.Parent = ScreenGui
Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.132681563, 0, 0.168169215, 0)
Frame.Size = UDim2.new(0, 375, 0, 267)

TextLabel.Parent = Frame
TextLabel.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
TextLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.BorderSizePixel = 0
TextLabel.Size = UDim2.new(0, 375, 0, 50)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "TEAMDude09123 GUI V1"
TextLabel.TextColor3 = Color3.fromRGB(255, 85, 255)
TextLabel.TextScaled = true
TextLabel.TextSize = 14.000
TextLabel.TextWrapped = true

ImageLabel.Parent = TextLabel
ImageLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ImageLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
ImageLabel.BorderSizePixel = 0
ImageLabel.Position = UDim2.new(0, 0, 1, 0)
ImageLabel.Size = UDim2.new(0, 375, 0, 217)
ImageLabel.Image = "rbxassetid://16891921733"

Dude09123skybox.Name = "Dude09123 skybox"
Dude09123skybox.Parent = TextLabel
Dude09123skybox.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
Dude09123skybox.BorderColor3 = Color3.fromRGB(0, 0, 0)
Dude09123skybox.BorderSizePixel = 0
Dude09123skybox.Position = UDim2.new(0, 0, 1.36000001, 0)
Dude09123skybox.Size = UDim2.new(0, 109, 0, 50)
Dude09123skybox.Font = Enum.Font.SourceSans
Dude09123skybox.Text = "Dude09123 skybox"
Dude09123skybox.TextColor3 = Color3.fromRGB(255, 255, 0)
Dude09123skybox.TextScaled = true
Dude09123skybox.TextSize = 14.000
Dude09123skybox.TextWrapped = true

Dude09123theme.Name = "Dude09123 theme"
Dude09123theme.Parent = Dude09123skybox
Dude09123theme.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
Dude09123theme.BorderColor3 = Color3.fromRGB(0, 0, 0)
Dude09123theme.BorderSizePixel = 0
Dude09123theme.Position = UDim2.new(0, 0, 1.51999998, 0)
Dude09123theme.Size = UDim2.new(0, 109, 0, 50)
Dude09123theme.Font = Enum.Font.SourceSans
Dude09123theme.Text = "Dude09123 theme"
Dude09123theme.TextColor3 = Color3.fromRGB(255, 255, 0)
Dude09123theme.TextScaled = true
Dude09123theme.TextSize = 14.000
Dude09123theme.TextWrapped = true

decalspam.Name = "decal spam"
decalspam.Parent = Dude09123theme
decalspam.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
decalspam.BorderColor3 = Color3.fromRGB(0, 0, 0)
decalspam.BorderSizePixel = 0
decalspam.Position = UDim2.new(0, 0, 1.46000004, 0)
decalspam.Size = UDim2.new(0, 109, 0, 50)
decalspam.Font = Enum.Font.SourceSans
decalspam.Text = "decal spam"
decalspam.TextColor3 = Color3.fromRGB(255, 255, 0)
decalspam.TextScaled = true
decalspam.TextSize = 14.000
decalspam.TextWrapped = true

teamcamerontheme.Name = "teamcameron theme"
teamcamerontheme.Parent = decalspam
teamcamerontheme.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
teamcamerontheme.BorderColor3 = Color3.fromRGB(0, 0, 0)
teamcamerontheme.BorderSizePixel = 0
teamcamerontheme.Position = UDim2.new(2.22018337, 0, 0, 0)
teamcamerontheme.Size = UDim2.new(0, 133, 0, 50)
teamcamerontheme.Font = Enum.Font.SourceSans
teamcamerontheme.Text = "teamcameron theme"
teamcamerontheme.TextColor3 = Color3.fromRGB(255, 255, 0)
teamcamerontheme.TextScaled = true
teamcamerontheme.TextSize = 14.000
teamcamerontheme.TextWrapped = true

disco.Name = "disco"
disco.Parent = teamcamerontheme
disco.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
disco.BorderColor3 = Color3.fromRGB(0, 0, 0)
disco.BorderSizePixel = 0
disco.Position = UDim2.new(0, 0, -1.46000004, 0)
disco.Size = UDim2.new(0, 133, 0, 50)
disco.Font = Enum.Font.SourceSans
disco.Text = "disco"
disco.TextColor3 = Color3.fromRGB(255, 255, 0)
disco.TextScaled = true
disco.TextSize = 14.000
disco.TextWrapped = true

hint.Name = "hint"
hint.Parent = disco
hint.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
hint.BorderColor3 = Color3.fromRGB(0, 0, 0)
hint.BorderSizePixel = 0
hint.Position = UDim2.new(0, 0, -1.51999998, 0)
hint.Size = UDim2.new(0, 133, 0, 50)
hint.Font = Enum.Font.SourceSans
hint.Text = "hint"
hint.TextColor3 = Color3.fromRGB(255, 255, 0)
hint.TextScaled = true
hint.TextSize = 14.000
hint.TextWrapped = true

TextLabel_2.Parent = hint
TextLabel_2.BackgroundColor3 = Color3.fromRGB(85, 85, 255)
TextLabel_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel_2.BorderSizePixel = 0
TextLabel_2.Position = UDim2.new(-0.939849615, 0, 3.68000007, 0)
TextLabel_2.Size = UDim2.new(0, 119, 0, 15)
TextLabel_2.Font = Enum.Font.SourceSans
TextLabel_2.Text = "made by teamcameron"
TextLabel_2.TextColor3 = Color3.fromRGB(255, 85, 255)
TextLabel_2.TextScaled = true
TextLabel_2.TextSize = 14.000
TextLabel_2.TextWrapped = true

-- Scripts:

local function FRORXO_fake_script() -- hint.Script 
	local script = Instance.new('Script', hint)

	script.Parent.MouseButton1Down:Connect(function()
		local function write(text,object)
			if object:IsA("Hint") == true then
				local count = object:FindFirstChild("Count")
				if count == nil then
					count = Instance.new("NumberValue")
					count.Parent = object
					count.Name = "Count"
					count.Value = count.Value + 1
				else
					count.Value = count.Value + 1
				end
				local startcount = count.Value
				for i = 1,#text do
					if count.Value == startcount then
						local letter = string.sub(text,i,i)
						object.Text = string.sub(text,1,i)
						wait(0.001)
					else
						break
					end
				end
			end
		end
		local bro = Instance.new("Hint",workspace)
		write("TEAMDude09123 join today!",bro)
	end)
	
end
coroutine.wrap(FRORXO_fake_script)()
local function CQWNL_fake_script() -- disco.Script 
	local script = Instance.new('Script', disco)

	
	--disco
	script.Parent.MouseButton1Click:Connect(function()
		local Lighting = game:GetService("Lighting")
		local ColorCorrection = Instance.new("ColorCorrectionEffect", Lighting)
	
		function zigzag(X) 
			return math.acos(math.cos(X*math.pi))/math.pi
		end
	
		Counter = 0
	
		Lighting.TimeOfDay = "12:00"
	
		while wait(0.1) do 
			ColorCorrection.TintColor = Color3.fromHSV(zigzag(Counter),1,1)
			Lighting.Ambient = Color3.fromHSV(zigzag(Counter),1,1)
			Counter += 0.01
		end
	end)
	
	
	
end
coroutine.wrap(CQWNL_fake_script)()
local function WOLSD_fake_script() -- teamcamerontheme.Script 
	local script = Instance.new('Script', teamcamerontheme)

	function onClick()
		Instance.new("Sound").Parent = game.Workspace  game.Workspace.Sound.SoundId ="rbxassetid://1839246711" game.Workspace.Sound.Looped=true  game.Workspace.Sound:Play()
	end
	
	script.Parent.MouseButton1Down:connect(onClick)
	
	
	
	
end
coroutine.wrap(WOLSD_fake_script)()
local function VHMV_fake_script() -- decalspam.Script 
	local script = Instance.new('Script', decalspam)

	function click()
		function exPro(root)
			for _, v in pairs(root:GetChildren()) do
				if v:IsA("Decal") and v.Texture ~= "http://www.roblox.com/asset/?id=16891921733" then
					v.Parent = nil
				elseif v:IsA("BasePart") then
					v.Material = "Plastic"
					v.Transparency = 0
					local One = Instance.new("Decal", v)
					local Two = Instance.new("Decal", v)
					local Three = Instance.new("Decal", v)
					local Four = Instance.new("Decal", v)
					local Five = Instance.new("Decal", v)
					local Six = Instance.new("Decal", v)
					One.Texture = "http://www.roblox.com/asset/?id=16891921733"
					Two.Texture = "http://www.roblox.com/asset/?id=16891921733"
					Three.Texture = "http://www.roblox.com/asset/?id=16891921733"
					Four.Texture = "http://www.roblox.com/asset/?id=16891921733"
					Five.Texture = "http://www.roblox.com/asset/?id=16891921733"
					Six.Texture = "http://www.roblox.com/asset/?id=16891921733"
					One.Face = "Front"
					Two.Face = "Back"
					Three.Face = "Right"
					Four.Face = "Left"
					Five.Face = "Top"
					Six.Face = "Bottom"
				end
				exPro(v)
			end
		end
		function asdf(root)
			for _, v in pairs(root:GetChildren()) do
				asdf(v)
			end
		end
		exPro(game.Workspace)
		asdf(game.Workspace)
	end
	
	script.Parent.MouseButton1Down:connect(click)
	
	
	--16891921733
	
end
coroutine.wrap(VHMV_fake_script)()
local function EOFECBS_fake_script() -- Dude09123theme.Script 
	local script = Instance.new('Script', Dude09123theme)

	function onClick()
		Instance.new("Sound").Parent = game.Workspace  game.Workspace.Sound.SoundId ="rbxassetid://142376088" game.Workspace.Sound.Looped=true  game.Workspace.Sound:Play()
	end
	
	script.Parent.MouseButton1Down:connect(onClick)
	
	
	
end
coroutine.wrap(EOFECBS_fake_script)()
local function IFDVSFS_fake_script() -- Dude09123skybox.Script 
	local script = Instance.new('Script', Dude09123skybox)

	--sky
	function click()
		s = Instance.new("Sky")
		s.Name = "Sky"
		s.Parent = game.Lighting
		s.SkyboxBk = "http://www.roblox.com/asset/?id=16891921733"
		s.SkyboxDn = "http://www.roblox.com/asset/?id=16891921733"
		s.SkyboxFt = "http://www.roblox.com/asset/?id=16891921733"
		s.SkyboxLf = "http://www.roblox.com/asset/?id=16891921733"
		s.SkyboxRt = "http://www.roblox.com/asset/?id=16891921733"
		s.SkyboxUp = "http://www.roblox.com/asset/?id=16891921733"
		game.Lighting.TimeOfDay = 12
	end
	
	script.Parent.MouseButton1Down:connect(click)
	
	
	
end
coroutine.wrap(IFDVSFS_fake_script)()
local function QRNC_fake_script() -- Frame.Script 
	local script = Instance.new('Script', Frame)

	script.Parent.Active = true
	script.Parent.Draggable = true
	
end
coroutine.wrap(QRNC_fake_script)()
  print("Clicked")
  end
})
--[[
Name = "Text" >> Button Text (String)
Callback = function(Value) -button press function
-- function here
end --end function
]]

local Tab1 = NewTab({Name = "scripts", Icon = "IconName"})
--[[
Name = "TabName" >> UI Button TabName (String)
Icon = "IconName" >> Tab Icon, No Need Put Id, You can get Icons In:.
https://github.com/Darkmoonxhubscript/DarkLibV2/blob/main/Icons.luau
]]

local Paragraph1 = AddParagraph(Tab1, {
  Name = "Sigma Sigma",
  SubText = "Boy Sigma Boy"
})
--[[
Name = "My Title" >> Paragraph Title (String)
SubText = "My Paragraph" >> Paragraph Text (String)
]]

local Button1 = AddButton(Tab1, {
  Name = "blackohle",
  Callback = function()-- Gui to Lua
-- Version: 3.2

-- Instances:

local Gui = Instance.new("ScreenGui")
local Main = Instance.new("Frame")
local Box = Instance.new("TextBox")
local UITextSizeConstraint = Instance.new("UITextSizeConstraint")
local Label = Instance.new("TextLabel")
local UITextSizeConstraint_2 = Instance.new("UITextSizeConstraint")
local Button = Instance.new("TextButton")
local UITextSizeConstraint_3 = Instance.new("UITextSizeConstraint")

--Properties:

Gui.Name = "Gui"
Gui.Parent = gethui()
Gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Main.Name = "Main"
Main.Parent = Gui
Main.BackgroundColor3 = Color3.fromRGB(75, 75, 75)
Main.BorderColor3 = Color3.fromRGB(0, 0, 0)
Main.BorderSizePixel = 0
Main.Position = UDim2.new(0.335954279, 0, 0.542361975, 0)
Main.Size = UDim2.new(0.240350261, 0, 0.166880623, 0)
Main.Active = true
Main.Draggable = true

Box.Name = "Box"
Box.Parent = Main
Box.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Box.BorderColor3 = Color3.fromRGB(0, 0, 0)
Box.BorderSizePixel = 0
Box.Position = UDim2.new(0.0980926454, 0, 0.218712583, 0)
Box.Size = UDim2.new(0.801089942, 0, 0.364963502, 0)
Box.FontFace = Font.new("rbxasset://fonts/families/SourceSansSemibold.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Box.PlaceholderText = "Player here"
Box.Text = ""
Box.TextColor3 = Color3.fromRGB(255, 255, 255)
Box.TextScaled = true
Box.TextSize = 31.000
Box.TextWrapped = true

UITextSizeConstraint.Parent = Box
UITextSizeConstraint.MaxTextSize = 31

Label.Name = "Label"
Label.Parent = Main
Label.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Label.BorderColor3 = Color3.fromRGB(0, 0, 0)
Label.BorderSizePixel = 0
Label.Size = UDim2.new(1, 0, 0.160583943, 0)
Label.FontFace = Font.new("rbxasset://fonts/families/Nunito.json", Enum.FontWeight.Bold, Enum.FontStyle.Normal)
Label.Text = "Bring Parts BY:TEAM KJJ HUB | t.me/team KJJ HUB"
Label.TextColor3 = Color3.fromRGB(255, 255, 255)
Label.TextScaled = true
Label.TextSize = 14.000
Label.TextWrapped = true

UITextSizeConstraint_2.Parent = Label
UITextSizeConstraint_2.MaxTextSize = 21

Button.Name = "Button"
Button.Parent = Main
Button.BackgroundColor3 = Color3.fromRGB(95, 95, 95)
Button.BorderColor3 = Color3.fromRGB(0, 0, 0)
Button.BorderSizePixel = 0
Button.Position = UDim2.new(0.183284417, 0, 0.656760991, 0)
Button.Size = UDim2.new(0.629427791, 0, 0.277372271, 0)
Button.Font = Enum.Font.Nunito
Button.Text = "Bring | Off"
Button.TextColor3 = Color3.fromRGB(255, 255, 255)
Button.TextScaled = true
Button.TextSize = 28.000
Button.TextWrapped = true

UITextSizeConstraint_3.Parent = Button
UITextSizeConstraint_3.MaxTextSize = 28

-- Scripts:

local Players = game:GetService("Players")
local RunService = game:GetService("RunService")
local LocalPlayer = Players.LocalPlayer
local UserInputService = game:GetService("UserInputService")
local Workspace = game:GetService("Workspace")

local character
local humanoidRootPart

mainStatus = true
UserInputService.InputBegan:Connect(function(input, gameProcessedEvent)
	if input.KeyCode == Enum.KeyCode.RightControl and not gameProcessedEvent then
		mainStatus = not mainStatus
		Main.Visible = mainStatus
	end
end)

local Folder = Instance.new("Folder", Workspace)
local Part = Instance.new("Part", Folder)
local Attachment1 = Instance.new("Attachment", Part)
Part.Anchored = true
Part.CanCollide = false
Part.Transparency = 1

if not getgenv().Network then
	getgenv().Network = {
		BaseParts = {},
		Velocity = Vector3.new(14.46262424, 14.46262424, 14.46262424)
	}

	Network.RetainPart = function(Part)
		if Part:IsA("BasePart") and Part:IsDescendantOf(Workspace) then
			table.insert(Network.BaseParts, Part)
			Part.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
			Part.CanCollide = false
		end
	end

	local function EnablePartControl()
		LocalPlayer.ReplicationFocus = Workspace
		RunService.Heartbeat:Connect(function()
			sethiddenproperty(LocalPlayer, "SimulationRadius", math.huge)
			for _, Part in pairs(Network.BaseParts) do
				if Part:IsDescendantOf(Workspace) then
					Part.Velocity = Network.Velocity
				end
			end
		end)
	end

	EnablePartControl()
end

local function ForcePart(v)
	if v:IsA("BasePart") and not v.Anchored and not v.Parent:FindFirstChildOfClass("Humanoid") and not v.Parent:FindFirstChild("Head") and v.Name ~= "Handle" then
		for _, x in ipairs(v:GetChildren()) do
			if x:IsA("BodyMover") or x:IsA("RocketPropulsion") then
				x:Destroy()
			end
		end
		if v:FindFirstChild("Attachment") then
			v:FindFirstChild("Attachment"):Destroy()
		end
		if v:FindFirstChild("AlignPosition") then
			v:FindFirstChild("AlignPosition"):Destroy()
		end
		if v:FindFirstChild("Torque") then
			v:FindFirstChild("Torque"):Destroy()
		end
		v.CanCollide = false
		local Torque = Instance.new("Torque", v)
		Torque.Torque = Vector3.new(100000, 100000, 100000)
		local AlignPosition = Instance.new("AlignPosition", v)
		local Attachment2 = Instance.new("Attachment", v)
		Torque.Attachment0 = Attachment2
		AlignPosition.MaxForce = math.huge
		AlignPosition.MaxVelocity = math.huge
		AlignPosition.Responsiveness = 200
		AlignPosition.Attachment0 = Attachment2
		AlignPosition.Attachment1 = Attachment1
	end
end

local blackHoleActive = false
local DescendantAddedConnection

local function toggleBlackHole()
	blackHoleActive = not blackHoleActive
	if blackHoleActive then
		Button.Text = "Bring Parts | On"
		for _, v in ipairs(Workspace:GetDescendants()) do
			ForcePart(v)
		end

		DescendantAddedConnection = Workspace.DescendantAdded:Connect(function(v)
			if blackHoleActive then
				ForcePart(v)
			end
		end)

		spawn(function()
			while blackHoleActive and RunService.RenderStepped:Wait() do
				Attachment1.WorldCFrame = humanoidRootPart.CFrame
			end
		end)
	else
		Button.Text = "Bring Parts | Off"
		if DescendantAddedConnection then
			DescendantAddedConnection:Disconnect()
		end
	end
end

local function getPlayer(name)
	local lowerName = string.lower(name)
	for _, p in pairs(Players:GetPlayers()) do
		local lowerPlayer = string.lower(p.Name)
		if string.find(lowerPlayer, lowerName) then
			return p
		elseif string.find(string.lower(p.DisplayName), lowerName) then
			return p
		end
	end
end

local player = nil

local function VDOYZQL_fake_script() -- Box.Script 
	local script = Instance.new('Script', Box)

	script.Parent.FocusLost:Connect(function(enterPressed)
		if enterPressed then
			player = getPlayer(Box.Text)
			if player then
				Box.Text = player.Name
				print("Player found:", player.Name)
			else
				print("Player not found")
			end
		end
	end)
end
coroutine.wrap(VDOYZQL_fake_script)()
local function JUBNQKI_fake_script() -- Button.Script 
	local script = Instance.new('Script', Button)

	script.Parent.MouseButton1Click:Connect(function()
		if player then
			character = player.Character or player.CharacterAdded:Wait()
			humanoidRootPart = character:WaitForChild("HumanoidRootPart")
			toggleBlackHole()
		else
			print("Player is not selected")
		end
	end)
end
coroutine.wrap(JUBNQKI_fake_script)()

  print("Clicked")
  end
})

--[[
Name = "Text" >> Button Text (String)
Callback = function(Value) -button press function
-- function here
end --end function
]]

local Tab1 = NewTab({Name = "credits", Icon = "IconName"})
--[[
Name = "TabName" >> UI Button TabName (String)
Icon = "IconName" >> Tab Icon, No Need Put Id, You can get Icons In:.
https://github.com/Darkmoonxhubscript/DarkLibV2/blob/main/Icons.luau
]]

local ServerInvite = AddDiscordInvite(Tab1, {
  Name = "junte-se ao serve pa se diverti",
  Description = "entra ae no discord ae",
  Logo = "Id",
  Invite = "https://discord.gg/wnRGwqnZ",
})

local Section1 = AddSection(Tab1, {Name = "em breve vai ter mais atualizacoes"})
--[[
Name = "Text" >> Text Of Section (String)
]]

local TextLabel1 = AddTextLabel(Tab1, {
  Name = "script criado por"
})

local TextLabel1 = AddTextLabel(Tab1, {
  Name = "frostxrzz7 e luckstarz"
})
