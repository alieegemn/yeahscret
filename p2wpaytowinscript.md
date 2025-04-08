local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end -- Ignore if the game has already processed the input
    if input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.Y then
        Time = 1 -- seconds
repeat wait() until game:IsLoaded()
wait(Time)
local PlaceID = game.PlaceId
local AllIDs = {}
local foundAnything = ""
local actualHour = os.date("!*t").hour
local Deleted = false
function TPReturner()
   local Site;
   if foundAnything == "" then
       Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100'))
   else
       Site = game.HttpService:JSONDecode(game:HttpGet('https://games.roblox.com/v1/games/' .. PlaceID .. '/servers/Public?sortOrder=Asc&limit=100&cursor=' .. foundAnything))
   end
   local ID = ""
   if Site.nextPageCursor and Site.nextPageCursor ~= "null" and Site.nextPageCursor ~= nil then
       foundAnything = Site.nextPageCursor
   end
   local num = 0;
   for i,v in pairs(Site.data) do
       local Possible = true
       ID = tostring(v.id)
       if tonumber(v.maxPlayers) > tonumber(v.playing) then
           for _,Existing in pairs(AllIDs) do
               if num ~= 0 then
                   if ID == tostring(Existing) then
                       Possible = false
                   end
               else
                   if tonumber(actualHour) ~= tonumber(Existing) then
                       local delFile = pcall(function()
                           delfile("NotSameServers.json")
                           AllIDs = {}
                           table.insert(AllIDs, actualHour)
                       end)
                   end
               end
               num = num + 1
           end
           if Possible == true then
               table.insert(AllIDs, ID)
               wait()
               pcall(function()
                   writefile("NotSameServers.json", game:GetService('HttpService'):JSONEncode(AllIDs))
                   wait()
                   game:GetService("TeleportService"):TeleportToPlaceInstance(PlaceID, ID, game.Players.LocalPlayer)
               end)
               wait(4)
           end
       end
   end
end

function Teleport()
   while wait() do
       pcall(function()
           TPReturner()
           if foundAnything ~= "" then
               TPReturner()
           end
       end)
   end
end

-- If you'd like to use a script before server hopping (Like a Automatic Chest collector you can put the Teleport() after it collected everything.
Teleport()


    end
end)

local UserInputService = game:GetService("UserInputService")

UserInputService.InputBegan:Connect(function(input, gameProcessed)
    if gameProcessed then return end -- Ignore if the game has already processed the input
    if input.UserInputType == Enum.UserInputType.Keyboard and input.KeyCode == Enum.KeyCode.R then
        game.Players.LocalPlayer:Kick("reload is loading")
wait("2")

game.Players.LocalPlayer:Kick("loading please wait...")

local ts = game:GetService("TeleportService")

local p = game:GetService("Players").LocalPlayer

 

ts:Teleport(game.PlaceId, p)
    end
end)


--Player Info
_G.HeadSize = 15000
_G.Disabled = true
 

--Don't Touch
game:GetService('RunService').RenderStepped:connect(function()
if _G.Disabled then
for i,v in next, game:GetService('Players'):GetPlayers() do
if v.Name ~= game:GetService('Players').LocalPlayer.Name then
pcall(function()
v.Character.HumanoidRootPart.Size = Vector3.new(_G.HeadSize,_G.HeadSize,_G.HeadSize)
--TRANSPARENCY of the HITBOX
v.Character.HumanoidRootPart.Transparency = 1
v.Character.HumanoidRootPart.BrickColor = BrickColor.new("Really blue")
v.Character.HumanoidRootPart.Material = "Neon"
v.Character.HumanoidRootPart.CanCollide = false
end)
end
end
end
end)


while true do
    wait()
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(82.0696106, 39.8481121, -12.5802393, -0.346195102, 0, 0.938162565, 0, 1, 0, 0.938162565, 0, -0.346195102)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(76.3158951, 35.759716, -5.75866795, -0.317335278, 2.02473416e-08, 0.948313415, -2.85272383e-09, 1, -2.23055068e-08, -0.948313415, -9.7836006e-09, -0.317335278)
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(83.0696106, 39.8481121, -29.5802393, -0.346195102, 0, 0.938162565, 0, 1, 0, -0.938162565, 0, -0.346195102)
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(83.0696106, 39.8481121, -29.5802393, -0.346195102, 0, 0.938162565, 0, 1, 0, -0.938162565, 0, -0.346195102)
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(82.0696106, 39.8481121, -12.5802393, -0.346195102, 0, 0.938162565, 0, 1, 0, 0.938162565, 0, -0.346195102)
									game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(82.0696106, 39.8481121, -12.5802393, -0.346195102, 0, 0.938162565, 0, 1, 0, 0.938162565, 0, -0.346195102)
								game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(82.0696106, 39.8481121, -12.5802393, -0.346195102, 0, 0.938162565, 0, 1, 0, 0.938162565, 0, -0.346195102)
						game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(96.229332, 36.6742477, -12.6924105, 0.199678257, 6.13518978e-08, 0.979861498, 1.17773617e-07, 1, -8.66129852e-08, -0.979861498, 1.3269657e-07, 0.199678257)
	local player = game.Players.LocalPlayer -- Get the player
local backpack = player.Backpack -- Access the player's backpack

-- Replace "ToolName" with the actual name of the tool you want to equip
local toolName = "ClassicSword" 

-- Find the tool in the backpack
local tool = backpack:FindFirstChild(toolName)

-- Equip the tool if it exists
if tool then
    -- Parent the tool to the character to equip it
    tool.Parent = player.Character
    tool.Handle.Massless = true -- Optional: If you want to disable any mass for the tool
end


end

end
