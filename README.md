local DiscordLib =
    loadstring(game:HttpGet "https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/discord")()
local win = DiscordLib:Window("discord library")
local serv = win:Server("Dolly x hub", "")

local tgls = serv:Channel("หน้าหลัก")
tgls:Toggle(
    "วาปไปจุดขายยา",
    false,
    function(bool)
        local TweenService = game:GetService("TweenService")
local Tw=
TweenService:Create(game.Players.LocalPlayer.Character. HumanoidRootPart, TweenInfo.new(1, Enum.EasingStyle.Linear,Enum.EasingDirection. Out,0,false,0),
{CFrame = CFrame.new(-1061.3543701171875, 1509.399658203125, -1443.5123291015625)}):Play()
    end
)

tgls:Toggle(
    "วาปไปจุดรับยา",
    false,
    function(bool)
        local TweenService = game:GetService("TweenService")
local Tw=
TweenService:Create(game.Players.LocalPlayer.Character. HumanoidRootPart, TweenInfo.new(1, Enum.EasingStyle.Linear,Enum.EasingDirection. Out,0,false,0),
{CFrame = CFrame.new(-663.4750366210938, 1509.515625, -1492.1463623046875)}):Play()
    end
)
local tgls = serv:Channel("ร้านค้า")
tgls:Toggle(
    "วาปไปหาคนขายอีโบ๊",
    false,
    function(bool)
        local TweenService = game:GetService("TweenService")
local Tw=
TweenService:Create(game.Players.LocalPlayer.Character. HumanoidRootPart, TweenInfo.new(1, Enum.EasingStyle.Linear,Enum.EasingDirection. Out,0,false,0),
{CFrame = CFrame.new(-1667.65771484375, 1509.5870361328125, -1097.9957275390625)}):Play()
    end
)
tgls:Toggle(
    "วาปไปหาคนขายคาตานะ",
    false,
    function(bool)
        local TweenService = game:GetService("TweenService")
local Tw=
TweenService:Create(game.Players.LocalPlayer.Character. HumanoidRootPart, TweenInfo.new(1, Enum.EasingStyle.Linear,Enum.EasingDirection. Out,0,false,0),
{CFrame = CFrame.new(-1529.153564453125, 1509.5870361328125, -1857.9334716796875)}):Play()
    end
)
tgls:Toggle(
    "วาปไปหาคนขายบาเร็ตต้า",
    false,
    function(bool)
        local TweenService = game:GetService("TweenService")
local Tw=
TweenService:Create(game.Players.LocalPlayer.Character. HumanoidRootPart, TweenInfo.new(1, Enum.EasingStyle.Linear,Enum.EasingDirection. Out,0,false,0),
{CFrame = CFrame.new(-2147.065185546875, 1509.7998046875, -1026.19775390625)}):Play()
    end
)
local tgls = serv:Channel("มอง")
tgls:Toggle(
    "มองผู้เล่น",
    false,
    function(bool)
 -- สคริปต์ ESP แสดงชื่อผู้เล่นและระยะห่าง

local function createESP(player)
    local character = player.Character
    if character and character:FindFirstChild("HumanoidRootPart") then
        -- สร้าง BillboardGui
        local esp = Instance.new("BillboardGui", character.HumanoidRootPart)
        esp.Name = "ESP"
        esp.Size = UDim2.new(0, 100, 0, 25)  -- ปรับขนาดลง 50%
        esp.AlwaysOnTop = true
        esp.Adornee = character.HumanoidRootPart
        esp.StudsOffset = Vector3.new(0, 3, 0) -- ปรับตำแหน่งของชื่อให้อยู่เหนือหัว

        -- สร้าง TextLabel สำหรับชื่อผู้เล่น
        local nameLabel = Instance.new("TextLabel", esp)
        nameLabel.Name = "NameLabel"
        nameLabel.Size = UDim2.new(1, 0, 0.5, 0)
        nameLabel.BackgroundTransparency = 1
        nameLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
        nameLabel.TextStrokeTransparency = 0.5
        nameLabel.TextScaled = true
        nameLabel.Text = player.Name

        -- สร้าง TextLabel สำหรับระยะห่าง
        local distanceLabel = Instance.new("TextLabel", esp)
        distanceLabel.Name = "DistanceLabel"
        distanceLabel.Size = UDim2.new(1, 0, 0.5, 0)
        distanceLabel.Position = UDim2.new(0, 0, 0.5, 0)
        distanceLabel.BackgroundTransparency = 1
        distanceLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
        distanceLabel.TextStrokeTransparency = 0.5
        distanceLabel.TextScaled = true

        -- ฟังก์ชันอัปเดตระยะห่าง
        local function updateDistance()
            if game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:FindFirstChild("HumanoidRootPart") then
                local myRootPart = game.Players.LocalPlayer.Character.HumanoidRootPart
                local distance = (character.HumanoidRootPart.Position - myRootPart.Position).Magnitude
                distanceLabel.Text = string.format("Distance: %.2f", distance)
            end
        end

        -- อัปเดตระยะห่างทุกเฟรม
        game:GetService("RunService").RenderStepped:Connect(updateDistance)
    end
end

local function removeESP(player)
    local character = player.Character
    if character and character:FindFirstChild("HumanoidRootPart") then
        local esp = character.HumanoidRootPart:FindFirstChild("ESP")
        if esp then
            esp:Destroy()
        end
    end
end

-- เชื่อมต่อฟังก์ชันเมื่อผู้เล่นเข้ามาในเกม
game.Players.PlayerAdded:Connect(function(player)
    player.CharacterAdded:Connect(function(character)
        wait(1) -- รอให้ตัวละครโหลดเสร็จ
        createESP(player)
    end)
end)

-- เชื่อมต่อฟังก์ชันเมื่อผู้เล่นออกจากเกม
game.Players.PlayerRemoving:Connect(function(player)
    removeESP(player)
end)

-- เพิ่มชื่อผู้เล่นให้ผู้เล่นที่มีอยู่ในเกมตอนนี้
for _, player in ipairs(game.Players:GetPlayers()) do
    if player.Character then
        createESP(player)
    end
    player.CharacterAdded:Connect(function(character)
        wait(1) -- รอให้ตัวละครโหลดเสร็จ
        createESP(player)
    end)
end

    end
)
local tgls = serv:Channel("ต่อสู้")
tgls:Toggle(
    "อิมล็อก",
    false,
    function(bool)
    -- ฟังก์ชันหาผู้เล่นที่อยู่ใกล้ที่สุดในระยะ 35 เมตร
function findClosestPlayer()
    local players = game.Players:GetPlayers()
    local closestDistance = 100  -- ระยะทางสูงสุดที่ต้องการล็อกเป้าหมาย
    local closestPlayer = nil
    local myCharacter = game.Players.LocalPlayer.Character

    for i, player in ipairs(players) do
        if player ~= game.Players.LocalPlayer then
            local playerCharacter = player.Character
            if playerCharacter and playerCharacter:FindFirstChild("HumanoidRootPart") and myCharacter and myCharacter:FindFirstChild("HumanoidRootPart") then
                local distance = (playerCharacter.HumanoidRootPart.Position - myCharacter.HumanoidRootPart.Position).magnitude
                if distance < closestDistance then

                    closestDistance = distance
                    closestPlayer = playerCharacter.HumanoidRootPart
                end
            end
        end
    end

    return closestPlayer
end

-- ฟังก์ชัน Aimlock
function aimlock()
    local target = findClosestPlayer()
    if target then
        -- เช็คว่าเป็นตัวเองหรือไม่
        if target.Parent ~= game.Players.LocalPlayer.Character then
            local camera = game.Workspace.CurrentCamera
            camera.CFrame = CFrame.new(camera.CFrame.Position, target.Position)
        end
    end
end

-- วนลูปเพื่อทำงานเป็นตัวติดตาม
while true do
    aimlock()
    wait(0.1)  -- รอเพื่อปรับความเร็วในการทำงาน (คุณสามารถปรับค่านี้ได้ตามต้องการ)
end
end)
