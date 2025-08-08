-- This script has been converted to FE by iPxter

if game:GetService("RunService"):IsClient() then error("Script must be server-side in order to work; use h/ and not hl/") end local Player,Mouse,mouse,UserInputService,ContextActionService = owner do print("FE Compatibility code by Mokiros | Translated to FE by iPxter") script.Parent = Player.Character

--RemoteEvent for communicating
local Event = Instance.new("RemoteEvent")
Event.Name = "UserInput_Event"

--Fake event to make stuff like Mouse.KeyDown work
local function fakeEvent()
	local t = {_fakeEvent=true,Connect=function(self,f)self.Function=f end}
	t.connect = t.Connect
	return t
end

--Creating fake input objects with fake variables
local m = {Target=nil,Hit=CFrame.new(),KeyUp=fakeEvent(),KeyDown=fakeEvent(),Button1Up=fakeEvent(),Button1Down=fakeEvent()}
local UIS = {InputBegan=fakeEvent(),InputEnded=fakeEvent()}
local CAS = {Actions={},BindAction=function(self,name,fun,touch,...)
	CAS.Actions[name] = fun and {Name=name,Function=fun,Keys={...}} or nil
end}
--Merged 2 functions into one by checking amount of arguments
CAS.UnbindAction = CAS.BindAction

--This function will trigger the events that have been :Connect()'ed
local function te(self,ev,...)
	local t = m[ev]
	if t and t._fakeEvent and t.Function then
		t.Function(...)
	end
end
m.TrigEvent = te
UIS.TrigEvent = te

Event.OnServerEvent:Connect(function(plr,io)
    if plr~=Player then return end
	if io.isMouse then
		m.Target = io.Target
		m.Hit = io.Hit
	else
		local b = io.UserInputState == Enum.UserInputState.Begin
		if io.UserInputType == Enum.UserInputType.MouseButton1 then
			return m:TrigEvent(b and "Button1Down" or "Button1Up")
		end
		for _,t in pairs(CAS.Actions) do
			for _,k in pairs(t.Keys) do
				if k==io.KeyCode then
					t.Function(t.Name,io.UserInputState,io)
				end
			end
		end
		m:TrigEvent(b and "KeyDown" or "KeyUp",io.KeyCode.Name:lower())
		UIS:TrigEvent(b and "InputBegan" or "InputEnded",io,false)
    end
end)
Event.Parent = NLS([==[
local Player = game:GetService("Players").LocalPlayer
local Event = script:WaitForChild("UserInput_Event")

local UIS = game:GetService("UserInputService")
local input = function(io,a)
	if a then return end
	--Since InputObject is a client-side instance, we create and pass table instead
	Event:FireServer({KeyCode=io.KeyCode,UserInputType=io.UserInputType,UserInputState=io.UserInputState})
end
UIS.InputBegan:Connect(input)
UIS.InputEnded:Connect(input)

local Mouse = Player:GetMouse()
local h,t
--Give the server mouse data 30 times every second, but only if the values changed
--If player is not moving their mouse, client won't fire events
while wait(1/30) do
	if h~=Mouse.Hit or t~=Mouse.Target then
		h,t=Mouse.Hit,Mouse.Target
		Event:FireServer({isMouse=true,Target=t,Hit=h})
	end
end]==],Player.Character)
Mouse,mouse,UserInputService,ContextActionService = m,m,UIS,CAS
end



wait(0.3)



Player = owner
PlayerGui = Player.PlayerGui
Cam = workspace.CurrentCamera
Backpack = Player.Backpack
Character = Player.Character
Humanoid = Character.Humanoid
Mouse = Player:GetMouse()
RootPart = Character["HumanoidRootPart"]
Torso = Character["Torso"]
Head = Character["Head"]
RightArm = Character["Right Arm"]
LeftArm = Character["Left Arm"]
RightLeg = Character["Right Leg"]
LeftLeg = Character["Left Leg"]
RootJoint = RootPart["RootJoint"]
Neck = Torso["Neck"]
RightShoulder = Torso["Right Shoulder"]
LeftShoulder = Torso["Left Shoulder"]
RightHip = Torso["Right Hip"]
LeftHip = Torso["Left Hip"]
hasdied = false
demon = false

IT = Instance.new
CF = CFrame.new
VT = Vector3.new
RAD = math.rad
C3 = Color3.new
UD2 = UDim2.new
BRICKC = BrickColor.new
ANGLES = CFrame.Angles
EULER = CFrame.fromEulerAnglesXYZ
COS = math.cos
ACOS = math.acos
SIN = math.sin
ASIN = math.asin
ABS = math.abs
MRANDOM = math.random
FLOOR = math.floor

function CreateMesh(MESH, PARENT, MESHTYPE, MESHID, TEXTUREID, SCALE, OFFSET)
	local NEWMESH = IT(MESH)
	if MESH == "SpecialMesh" then
		NEWMESH.MeshType = MESHTYPE
		if MESHID ~= "nil" and MESHID ~= "" then
			NEWMESH.MeshId = "http://www.roblox.com/asset/?id="..MESHID
		end
		if TEXTUREID ~= "nil" and TEXTUREID ~= "" then
			NEWMESH.TextureId = "http://www.roblox.com/asset/?id="..TEXTUREID
		end
	end
	NEWMESH.Offset = OFFSET or VT(0, 0, 0)
	NEWMESH.Scale = SCALE
	NEWMESH.Parent = PARENT
	return NEWMESH
end

function CreatePart(FORMFACTOR, PARENT, MATERIAL, REFLECTANCE, TRANSPARENCY, BRICKCOLOR, NAME, SIZE)
	local NEWPART = IT("Part")
	NEWPART.formFactor = FORMFACTOR
	NEWPART.Reflectance = REFLECTANCE
	NEWPART.Transparency = TRANSPARENCY
	NEWPART.CanCollide = false
	NEWPART.Locked = true
	NEWPART.BrickColor = BRICKC(tostring(BRICKCOLOR))
	NEWPART.Name = NAME
	NEWPART.Size = SIZE
	NEWPART.Position = Torso.Position
	NEWPART.Material = MATERIAL
	NEWPART:BreakJoints()
	NEWPART.Parent = PARENT
	return NEWPART
end


--//=================================\\
--||		  CUSTOMIZATION
--\\=================================//

Class_Name = "Chainiac"
Weapon_Name = "Chainiac"

Custom_Colors = {
	Custom_Color_1 = BRICKC("Institutional white"); --1st color for the weapon.
	Custom_Color_2 = BRICKC("Institutional white"); --2nd color for the weapon.

	Custom_Color_3 = BRICKC("Institutional white"); --Color for the abilities.
	Custom_Color_4 = BRICKC("Institutional white"); --Color for the secondary bar.
	Custom_Color_5 = BRICKC("Institutional white"); --Color for the mana bar.
	Custom_Color_6 = BRICKC("Institutional white"); --Color for the health bar.
	Custom_Color_7 = BRICKC("Institutional white"); --Color for the stun bar.

	Custom_Color_8 = BRICKC("Institutional white"); --Background for the mana bar.
	Custom_Color_9 = BRICKC("Institutional white"); --Background for the secondary mana bar.
	Custom_Color_10 = BRICKC("Institutional white"); --Background for the stun bar.
	Custom_Color_11 = BRICKC("Institutional white"); --Background for the health bar.
	Custom_Color_12 = BRICKC("Institutional white"); --Background for the abilities.
}

Mana_Bar_Background_Transparency = 0 --Transparency for the background of the mana bar.
Secondary_Mana_Bar_Background_Transparency = 0 --Transparency for the background of the secondary mana bar.
Health_Bar_Background_Transparency = 0 --Transparency for the background of the health bar.
Stun_Bar_Background_Transparency = 0 --Transparency for the background of the stun bar.
Ability_Background_Transparency = 0  --Transparency for the background of the abilities.
Stat_Background_Transparency = 0 --Transparency for the background of the stats.

Player_Size = 1 --Size of the player.
Animation_Speed = 5.2
Frame_Speed = 1 / 60 -- (1 / 30) OR (1 / 60)

Enable_Gui = false --Enables or disables the Weapon Gui. Also functions as hiding or showing the Gui.
Enable_Stats = false --Enables or disables stats.
Put_Stats_In_Character = false --Places stats in Character.
Enable_Stagger_Hit = false --Enables or disables staggering when hitting a hitbox of some sort.
Play_Hitbox_Hit_Sound = true --Plays a hit sound when hitting a hitbox of some sort.
Enable_Stagger = false --Enables or disables staggering.
Enable_Stun = false --Enables or disables the stun mechanic.
Enable_Abilities = false --Enables abilites with cooldowns and mana costs.
Enable_Secondary_Bar = false --Enables the secondary mana bar, if true.

Start_Equipped = false --Starts the player equipped with their weapon.
Start_Equipped_With_Equipped_Animation = false --Used in conjunction with the above option. Starts your equip animation.
Can_Equip_Or_Unequip = false --Enables or disables the ability to unequip or equip your weapon.
Disable_Animator = false --Disables the Animator in the humanoid.
Disable_Animate = true --Disables the Animate script in the character.
Disable_Moving_Arms = false --Keeps the arms from moving around.
Use_Motors_Instead_Of_Welds = false --Uses motors instead of welds to disable moving arms.
Walkspeed_Depends_On_Movement_Value = false --Walkspeed depends on movement value. Self-explanatory.
Disable_Jump = false --Disables jumping.
Use_HopperBin = false --Uses a hopperbin to do things.

Cooldown_1 = 0 --Cooldowns for abilites.
Cooldown_2 = 0
Cooldown_3 = 0
Cooldown_4 = 0
Skill_1_Mana_Cost = 0 --How much mana is required to use the skill.
Skill_2_Mana_Cost = 0
Skill_3_Mana_Cost = 0
Skill_4_Mana_Cost = 0
Max_Mana = 0 --Maximum amount of mana you can have.
Max_Secondary_Mana = 0 --Maximum amount of secondary mana you can have.
Mana_Name = "Mana" --Name for the mana bar.
Secondary_Mana_Name = "Block" --Name for the secondary mana bar.
Max_Stun = 1 --Maximum amount of stun you can have.
Recover_Mana = 0 --How much mana you gain.
Mana_Regen_Mode = "1" --Basically switches from one mana regen system to another.
Secondary_Mana_Regen_Mode = "1" --Basically switches from one secondary mana regen system to another.
Stun_Lose_Mode = "1" --Basically switches from one secondary stun loss system to another.
Recover_Secondary_Mana = 0 --How much secondary mana you gain.
Lose_Stun = 0 --How much stun you lose.
Stun_Wait = 0 --Delay between losing stun.
Mana_Wait = 0 --Delay between gaining mana.
Secondary_Mana_Wait = 0 --Delay between gaining secondary mana.
Menu_Update_Speed = 0 --How fast the Weapon Gui will update.
Constant_Update = false --Removes the delay between updating the Weapon GUI.
Show_Stats = false --Hides or shows stats.
Stat_Offset = 0.74 --For cosmetic purposes. {0.74, 0.78}

--//=================================\\
--|| 	  END OF CUSTOMIZATION
--\\=================================//

	local function weldBetween(a, b)
	    local weldd = Instance.new("ManualWeld")
	    weldd.Part0 = a
	    weldd.Part1 = b
	    weldd.C0 = CFrame.new()
	    weldd.C1 = b.CFrame:inverse() * a.CFrame
	    weldd.Parent = a
	    return weldd
	end

function createaccessory(attachmentpart,mesh,texture,scale,offset,color)
local acs = Instance.new("Part")
acs.CanCollide = false
acs.Anchored = false
acs.Size = Vector3.new(0,0,0)
acs.CFrame = attachmentpart.CFrame
acs.Parent = Character
acs.BrickColor = color
    local meshs = Instance.new("SpecialMesh")
    meshs.MeshId = mesh
    meshs.TextureId = texture
    meshs.Parent = acs
    meshs.Scale = scale
    meshs.Offset = offset
weldBetween(attachmentpart,acs)
end

local accessories = Instance.new("Folder",Character)
accessories.Name = "Add-ons"

function createbodypart(TYPE,COLOR,PART,OFFSET,SIZE)
if TYPE == "Gem" then
	local acs = CreatePart(3, accessories, "Plastic", 0, 0, COLOR, "Part", VT(0,0,0))
	acs.Anchored = false
    acs.CanCollide = false
	acs.CFrame = PART.CFrame
	local acs2 = CreateMesh("SpecialMesh", acs, "FileMesh", "9756362", "", SIZE, OFFSET)
weldBetween(PART,acs)
elseif TYPE == "Skull" then
	local acs = CreatePart(3, accessories, "Plastic", 0, 0, COLOR, "Part", VT(0,0,0))
	acs.Anchored = false
    acs.CanCollide = false
	acs.CFrame = PART.CFrame
	local acs2 = CreateMesh("SpecialMesh", acs, "FileMesh", "4770583", "", SIZE, OFFSET)
weldBetween(PART,acs)
elseif TYPE == "Eye" then
	local acs = CreatePart(3, accessories, "Neon", 0, 0, COLOR, "Part", VT(0,0,0))
	acs.Anchored = false
    acs.CanCollide = false
	acs.CFrame = PART.CFrame
	local acs2 = CreateMesh("SpecialMesh", acs, "Sphere", "", "", SIZE, OFFSET)
weldBetween(PART,acs)
end
end

--//=================================\\
--|| 	      USEFUL VALUES
--\\=================================//

local ROOTC0 = CF(0, 0, 0) * ANGLES(RAD(-90), RAD(0), RAD(180))
local NECKC0 = CF(0, 1, 0) * ANGLES(RAD(-90), RAD(0), RAD(180))
local RIGHTSHOULDERC0 = CF(-0.5, 0, 0) * ANGLES(RAD(0), RAD(90), RAD(0))
local LEFTSHOULDERC0 = CF(0.5, 0, 0) * ANGLES(RAD(0), RAD(-90), RAD(0))
local CO1 = 0
local CO2 = 0
local CO3 = 0
local CO4 = 0
local KEYHOLD = false
local CHANGEDEFENSE = 0
local CHANGEDAMAGE = 0
local CHANGEMOVEMENT = 0
local ANIM = "Idle"
local ATTACK = false
local EQUIPPED = false
local HOLD = false
local COMBO = 1
local LASTPOINT = nil
local BLCF = nil
local SCFR = nil
local STAGGERHITANIM = false
local STAGGERANIM = false
local STUNANIM = false
local CRITCHANCENUMBER = 0
local IDLENUMBER = 0
local DONUMBER = 0
local HANDIDLE = false
local SINE = 0
local CHANGE = 2 / Animation_Speed
local WALKINGANIM = false
local WALK = 0
local DISABLEJUMPING = false
local HASBEENBLOCKED = false
local INTRODONE = false
local STUNDELAYNUMBER = 0
local MANADELAYNUMBER = 0
local SECONDARYMANADELAYNUMBER = 0
local ROBLOXIDLEANIMATION = IT("Animation")
ROBLOXIDLEANIMATION.Name = "Roblox Idle Animation"
ROBLOXIDLEANIMATION.AnimationId = "http://www.roblox.com/asset/?id=180435571"
--ROBLOXIDLEANIMATION.Parent = Humanoid
local WEAPONGUI = IT("ScreenGui", nil)
WEAPONGUI.Name = "Weapon GUI"
local WEAPONTOOL = IT("HopperBin", nil)
WEAPONTOOL.Name = Weapon_Name
local Weapon = IT("Model")
Weapon.Name = Weapon_Name
local Effects = IT("Folder", Weapon)
Effects.Name = "Effects"
local ANIMATOR = Humanoid.Animator
local ANIMATE = Character.Animate
local HITPLAYERSOUNDS = {"703633905","264486467","356551938"}
local HITARMORSOUNDS = {"199149321", "199149338", "199149367", "199149409", "199149452"}
local HITWEAPONSOUNDS = {"199148971", "199149025", "199149072", "199149109", "199149119"}
local HITBLOCKSOUNDS = {"199148933", "199148947"}
local CHAINSAWIDLE = Instance.new("Sound",Torso)
CHAINSAWIDLE.SoundId = "rbxassetid://1165167610"
CHAINSAWIDLE.Volume = 3
CHAINSAWIDLE.Looped = true
local REV = Instance.new("Sound",Torso)
REV.SoundId = "rbxassetid://1165167936"
REV.Looped = true
REV.Volume = 1.6
local CHAINSAWSTRIKE = Instance.new("Sound",Torso)
CHAINSAWSTRIKE.Playing = false
CHAINSAWSTRIKE.SoundId = "rbxassetid://862701802"
local Taunt1 = Instance.new("Sound",Torso)
Taunt1.Volume = 3
Taunt1.SoundId = "rbxassetid://834001699"
local Taunt2 = Instance.new("Sound",Torso)
Taunt2.Volume = 3
Taunt2.SoundId = "rbxassetid://834001752"
local Taunt3 = Instance.new("Sound",Torso)
Taunt3.Volume = 3
Taunt3.SoundId = "rbxassetid://834001797"
local Taunt4 = Instance.new("Sound",Torso)
Taunt4.Volume = 3
Taunt4.SoundId = "rbxassetid://834001828"
local TAUNTS = {Taunt1,Taunt2,Taunt3,Taunt4}
local FRESHMEAT = Instance.new("Sound",Torso)
FRESHMEAT.Playing = false
FRESHMEAT.Volume = 5
FRESHMEAT.SoundId = "rbxassetid://2767085"
local sick = Instance.new("Sound",Character)
sick.SoundId = "rbxassetid://9038407107"
sick.Looped = true
sick.Pitch = 0.6
sick.Volume = 1
--//=================================\\
--\\=================================//

--//=================================\\
--||			  STATS
--\\=================================//

if Character:FindFirstChild("Stats") ~= nil then
Character:FindFirstChild("Stats").Parent = nil
end

local Stats = IT("Folder", nil)
Stats.Name = "Stats"
local ChangeStat = IT("Folder", Stats)
ChangeStat.Name = "ChangeStat"
local Defense = IT("NumberValue", Stats)
Defense.Name = "Defense"
Defense.Value = 1
local Movement = IT("NumberValue", Stats)
Movement.Name = "Movement"
Movement.Value = 1
local Damage = IT("NumberValue", Stats)
Damage.Name = "Damage"
Damage.Value = 1
local Mana = IT("NumberValue", Stats)
Mana.Name = "Mana"
Mana.Value = 0
local SecondaryMana = IT("NumberValue", Stats)
SecondaryMana.Name = "SecondaryMana"
SecondaryMana.Value = 0
local CanCrit = IT("BoolValue", Stats)
CanCrit.Name = "CanCrit"
CanCrit.Value = false
local CritChance = IT("NumberValue", Stats)
CritChance.Name = "CritChance"
CritChance.Value = 20
local CanPenetrateArmor = IT("BoolValue", Stats)
CanPenetrateArmor.Name = "CanPenetrateArmor"
CanPenetrateArmor.Value = false
local AntiTeamKill = IT("BoolValue", Stats)
AntiTeamKill.Name = "AntiTeamKill"
AntiTeamKill.Value = false
local Rooted = IT("BoolValue", Stats)
Rooted.Name = "Rooted"
Rooted.Value = false
local Block = IT("BoolValue", Stats)
Block.Name = "Block"
Block.Value = false
local RecentEnemy = IT("ObjectValue", Stats)
RecentEnemy.Name = "RecentEnemy"
RecentEnemy.Value = nil
local StaggerHit = IT("BoolValue", Stats)
StaggerHit.Name = "StaggerHit"
StaggerHit.Value = false
local Stagger = IT("BoolValue", Stats)
Stagger.Name = "Stagger"
Stagger.Value = false
local Stun = IT("BoolValue", Stats)
Stun.Name = "Stun"
Stun.Value = false
local StunValue = IT("NumberValue", Stats)
StunValue.Name = "StunValue"
StunValue.Value = 0

if Enable_Stats == true and Put_Stats_In_Character == true then
	Stats.Parent = Character
end

--//=================================\\
--\\=================================//





--//=================================\\
--|| 	     DEBUFFS / BUFFS
--\\=================================//

local DEFENSECHANGE1 = IT("NumberValue", ChangeStat)
DEFENSECHANGE1.Name = "ChangeDefense"
DEFENSECHANGE1.Value = 0

local MOVEMENTCHANGE1 = IT("NumberValue", nil)
MOVEMENTCHANGE1.Name = "ChangeMovement"
MOVEMENTCHANGE1.Value = 0

--//=================================\\
--\\=================================//





--//=================================\\
--|| SAZERENOS' ARTIFICIAL HEARTBEAT
--\\=================================//

ArtificialHB = Instance.new("BindableEvent", script)
ArtificialHB.Name = "ArtificialHB"

script:WaitForChild("ArtificialHB")

frame = Frame_Speed
tf = 0
allowframeloss = false
tossremainder = false
lastframe = tick()
script.ArtificialHB:Fire()

game:GetService("RunService").Heartbeat:connect(function(s, p)
	tf = tf + s
	if tf >= frame then
		if allowframeloss then
			script.ArtificialHB:Fire()
			lastframe = tick()
		else
			for i = 1, math.floor(tf / frame) do
				script.ArtificialHB:Fire()
			end
		lastframe = tick()
		end
		if tossremainder then
			tf = 0
		else
			tf = tf - frame * math.floor(tf / frame)
		end
	end
end)

--//=================================\\
--\\=================================//





--//=================================\\
--|| 	      SOME FUNCTIONS
--\\=================================//

function Raycast(POSITION, DIRECTION, RANGE, IGNOREDECENDANTS)
	return workspace:FindPartOnRay(Ray.new(POSITION, DIRECTION.unit * RANGE), IGNOREDECENDANTS)
end

function PositiveAngle(NUMBER)
	if NUMBER >= 0 then
		NUMBER = 0
	end
	return NUMBER
end

function NegativeAngle(NUMBER)
	if NUMBER <= 0 then
		NUMBER = 0
	end
	return NUMBER
end

function Swait(NUMBER)
	if NUMBER == 0 or NUMBER == nil then
		ArtificialHB.Event:wait()
	else
		for i = 1, NUMBER do
			ArtificialHB.Event:wait()
		end
	end
end

function QuaternionFromCFrame(cf)
	local mx, my, mz, m00, m01, m02, m10, m11, m12, m20, m21, m22 = cf:components()
	local trace = m00 + m11 + m22
	if trace > 0 then 
		local s = math.sqrt(1 + trace)
		local recip = 0.5 / s
		return (m21 - m12) * recip, (m02 - m20) * recip, (m10 - m01) * recip, s * 0.5
	else
		local i = 0
		if m11 > m00 then
			i = 1
		end
		if m22 > (i == 0 and m00 or m11) then
			i = 2
		end
		if i == 0 then
			local s = math.sqrt(m00 - m11 - m22 + 1)
			local recip = 0.5 / s
			return 0.5 * s, (m10 + m01) * recip, (m20 + m02) * recip, (m21 - m12) * recip
		elseif i == 1 then
			local s = math.sqrt(m11 - m22 - m00 + 1)
			local recip = 0.5 / s
			return (m01 + m10) * recip, 0.5 * s, (m21 + m12) * recip, (m02 - m20) * recip
		elseif i == 2 then
			local s = math.sqrt(m22 - m00 - m11 + 1)
			local recip = 0.5 / s return (m02 + m20) * recip, (m12 + m21) * recip, 0.5 * s, (m10 - m01) * recip
		end
	end
end
 
function QuaternionToCFrame(px, py, pz, x, y, z, w)
	local xs, ys, zs = x + x, y + y, z + z
	local wx, wy, wz = w * xs, w * ys, w * zs
	local xx = x * xs
	local xy = x * ys
	local xz = x * zs
	local yy = y * ys
	local yz = y * zs
	local zz = z * zs
	return CFrame.new(px, py, pz, 1 - (yy + zz), xy - wz, xz + wy, xy + wz, 1 - (xx + zz), yz - wx, xz - wy, yz + wx, 1 - (xx + yy))
end
 
function QuaternionSlerp(a, b, t)
	local cosTheta = a[1] * b[1] + a[2] * b[2] + a[3] * b[3] + a[4] * b[4]
	local startInterp, finishInterp;
	if cosTheta >= 0.0001 then
		if (1 - cosTheta) > 0.0001 then
			local theta = ACOS(cosTheta)
			local invSinTheta = 1 / SIN(theta)
			startInterp = SIN((1 - t) * theta) * invSinTheta
			finishInterp = SIN(t * theta) * invSinTheta
		else
			startInterp = 1 - t
			finishInterp = t
		end
	else
		if (1 + cosTheta) > 0.0001 then
			local theta = ACOS(-cosTheta)
			local invSinTheta = 1 / SIN(theta)
			startInterp = SIN((t - 1) * theta) * invSinTheta
			finishInterp = SIN(t * theta) * invSinTheta
		else
			startInterp = t - 1
			finishInterp = t
		end
	end
	return a[1] * startInterp + b[1] * finishInterp, a[2] * startInterp + b[2] * finishInterp, a[3] * startInterp + b[3] * finishInterp, a[4] * startInterp + b[4] * finishInterp
end

function Clerp(a, b, t)
	local qa = {QuaternionFromCFrame(a)}
	local qb = {QuaternionFromCFrame(b)}
	local ax, ay, az = a.x, a.y, a.z
	local bx, by, bz = b.x, b.y, b.z
	local _t = 1 - t
	return QuaternionToCFrame(_t * ax + t * bx, _t * ay + t * by, _t * az + t * bz, QuaternionSlerp(qa, qb, t))
end

function CreateFrame(PARENT, TRANSPARENCY, BORDERSIZEPIXEL, POSITION, SIZE, COLOR, BORDERCOLOR, NAME)
	local frame = IT("Frame")
	frame.BackgroundTransparency = TRANSPARENCY
	frame.BorderSizePixel = BORDERSIZEPIXEL
	frame.Position = POSITION
	frame.Size = SIZE
	frame.BackgroundColor3 = COLOR
	frame.BorderColor3 = BORDERCOLOR
	frame.Name = NAME
	frame.Parent = PARENT
	return frame
end

function CreateLabel(PARENT, TEXT, TEXTCOLOR, TEXTFONTSIZE, TEXTFONT, TRANSPARENCY, BORDERSIZEPIXEL, STROKETRANSPARENCY, NAME)
	local label = IT("TextLabel")
	label.BackgroundTransparency = 1
	label.Size = UD2(1, 0, 1, 0)
	label.Position = UD2(0, 0, 0, 0)
	label.TextColor3 = C3(255, 255, 255)
	label.TextStrokeTransparency = STROKETRANSPARENCY
	label.TextTransparency = TRANSPARENCY
	label.FontSize = TEXTFONTSIZE
	label.Font = TEXTFONT
	label.BorderSizePixel = BORDERSIZEPIXEL
	label.TextScaled = true
	label.Text = TEXT
	label.Name = NAME
	label.Parent = PARENT
	return label
end

function NoOutlines(PART)
	PART.TopSurface, PART.BottomSurface, PART.LeftSurface, PART.RightSurface, PART.FrontSurface, PART.BackSurface = 10, 10, 10, 10, 10, 10
end


function CreateWeldOrSnapOrMotor(TYPE, PARENT, PART0, PART1, C0, C1)
	local NEWWELD = IT(TYPE)
	NEWWELD.Part0 = PART0
	NEWWELD.Part1 = PART1
	NEWWELD.C0 = C0
	NEWWELD.C1 = C1
	NEWWELD.Parent = PARENT
	return NEWWELD
end

function CreateSound(ID, PARENT, VOLUME, PITCH)
	coroutine.resume(coroutine.create(function()
		local NEWSOUND = IT("Sound", PARENT)
		NEWSOUND.Volume = VOLUME
		NEWSOUND.Pitch = PITCH
		NEWSOUND.SoundId = "http://www.roblox.com/asset/?id="..ID
		Swait()
		NEWSOUND:play()
		game:GetService("Debris"):AddItem(NEWSOUND, 10)
	end))
end

function CFrameFromTopBack(at, top, back)
	local right = top:Cross(back)
	return CF(at.x, at.y, at.z, right.x, top.x, back.x, right.y, top.y, back.y, right.z, top.z, back.z)
end

function Lightning(POSITION1, POSITION2, MULTIPLIERTIME, LIGHTNINGDELAY, OFFSET, BRICKCOLOR, MATERIAL, SIZE, TRANSPARENCY, LASTINGTIME)
	local MAGNITUDE = (POSITION1 - POSITION2).magnitude 
	local CURRENTPOSITION = POSITION1
	local LIGHTNINGOFFSET = {-OFFSET, OFFSET}
	coroutine.resume(coroutine.create(function()
		for i = 1, MULTIPLIERTIME do 
			local LIGHTNINGPART = CreatePart(3, Effects, MATERIAL, 0, 0, BRICKCOLOR,"Effect", VT(SIZE * Player_Size, SIZE * Player_Size, MAGNITUDE / MULTIPLIERTIME))
			LIGHTNINGPART.Anchored = true
			local LIGHTNINGOFFSET2 = VT(LIGHTNINGOFFSET[MRANDOM(1, 2)], LIGHTNINGOFFSET[MRANDOM(1, 2)], LIGHTNINGOFFSET[MRANDOM(1, 2)]) 
			local LIGHTNINGPOSITION1 = CF(CURRENTPOSITION, POSITION2) * CF(0, 0, MAGNITUDE / MULTIPLIERTIME).p + LIGHTNINGOFFSET2
			if MULTIPLIERTIME == i then 
				local LIGHTNINGMAGNITUDE1 = (CURRENTPOSITION - POSITION2).magnitude
				LIGHTNINGPART.Size = VT(SIZE * Player_Size, SIZE * Player_Size, LIGHTNINGMAGNITUDE1)
				LIGHTNINGPART.CFrame = CF(CURRENTPOSITION, POSITION2) * CF(0, 0, -LIGHTNINGMAGNITUDE1 / 2)
			else
				LIGHTNINGPART.CFrame = CF(CURRENTPOSITION, LIGHTNINGPOSITION1) * CF(0, 0, MAGNITUDE / MULTIPLIERTIME / 2)
			end
			CURRENTPOSITION=LIGHTNINGPART.CFrame * CF(0, 0, MAGNITUDE / MULTIPLIERTIME / 2).p
			game.Debris:AddItem(LIGHTNINGPART, LASTINGTIME)
			coroutine.resume(coroutine.create(function()
				while LIGHTNINGPART.Transparency ~= 1 do
					--local StartTransparency = tra
					for i=0, 1, LASTINGTIME do
						Swait()
						LIGHTNINGPART.Transparency = LIGHTNINGPART.Transparency + (0.1 / LASTINGTIME)
					end
				end
			end))
		Swait(LIGHTNINGDELAY / Animation_Speed)
		end
	end))
end

--[[Usage:
	local Pos = Part
	local Offset = Part.CFrame * CF(0, 0, 0)
	local Color = "Institutional white"
	local Material = "Neon"
	local TheDelay = 0.01
	local Height = 4
	BLCF = Offset
	if SCFR and (Pos.Position - SCFR.p).magnitude > 0.1 then
		local a, b = Triangle(Color, Material, (SCFR * CF(0, Height / 2,0)).p, (SCFR * CF(0, -Height / 2, 0)).p, (BLCF * CF(0, Height / 2,0)).p, TheDelay)
		if a then game:GetService("Debris"):AddItem(a, 1) end
		if b then game:GetService("Debris"):AddItem(b, 1) end
		local a, b = Triangle(Color, Material, (BLCF * CF(0, Height / 2, 0)).p, (BLCF * CF(0, -Height / 2, 0)).p, (SCFR * CF(0, -Height / 2, 0)).p, TheDelay)
		if a then game:GetService("Debris"):AddItem(a, 1) end
		if b then game:GetService("Debris"):AddItem(b, 1) end
		SCFR = BLCF
	elseif not SCFR then
		SCFR = BLCF
	end
--
BLCF = nil
SCFR = nil
--]]

--//=================================\\
--\\=================================//





--//=================================\\
--||	      RESIZE PLAYER
--\\=================================//

if Player_Size ~= 1 then
RootPart.Size = RootPart.Size * Player_Size
Torso.Size = Torso.Size * Player_Size
Head.Size = Head.Size * Player_Size
RightArm.Size = RightArm.Size * Player_Size
LeftArm.Size = LeftArm.Size * Player_Size
RightLeg.Size = RightLeg.Size * Player_Size
LeftLeg.Size = LeftLeg.Size * Player_Size
RootJoint.Parent = RootPart
Neck.Parent = Torso
RightShoulder.Parent = Torso
LeftShoulder.Parent = Torso
RightHip.Parent = Torso
LeftHip.Parent = Torso
	
RootJoint.C0 = ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0))
	RootJoint.C1 = ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0))
	Neck.C0 = NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(0), RAD(0), RAD(0))
	Neck.C1 = CF(0 * Player_Size, -0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-90), RAD(0), RAD(180))
	RightShoulder.C0 = CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)) * RIGHTSHOULDERC0
	LeftShoulder.C0 = CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)) * LEFTSHOULDERC0
	if Disable_Moving_Arms == false then
		RightShoulder.C1 = ANGLES(0, RAD(90), 0) * CF(0 * Player_Size, 0.5 * Player_Size, -0.5)
		LeftShoulder.C1 = ANGLES(0, RAD(-90), 0) * CF(0 * Player_Size, 0.5 * Player_Size, -0.5)
	else
		RightShoulder.C1 = CF(0 * Player_Size, 0.5 * Player_Size, 0 * Player_Size)
		LeftShoulder.C1 = CF(0 * Player_Size, 0.5 * Player_Size, 0 * Player_Size)
	end
	RightHip.C0 = CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0))
	LeftHip.C0 = CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0))
	RightHip.C1 = CF(0.5 * Player_Size, 1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0))
	LeftHip.C1 = CF(-0.5 * Player_Size, 1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0))
--------------------
end


--//=================================\\
--\\=================================//




--//=================================\\
--||	     WEAPON CREATION
--\\=================================//

local HandlePart = CreatePart(3, Weapon, "SmoothPlastic", 1, 1, "Really black", "Handle", VT(0.25*Player_Size,0.25*Player_Size,1.5*Player_Size))
local HandleWeld = CreateWeldOrSnapOrMotor("Weld", HandlePart, RightArm, HandlePart, CF(0 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), CF(0, 0, 0))
local chainsaw = CreatePart(3, Weapon, "SmoothPlastic", 1, 1, "Reddish brown", "Handle", VT(1.2*Player_Size,1.2*Player_Size,5*Player_Size))
local axeweld = CreateWeldOrSnapOrMotor("Weld", HandlePart, chainsaw, HandlePart, CF(0 * Player_Size, 0 * Player_Size, 1.6 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), CF(0, 0, 0))
local HandleMesh = CreateMesh("SpecialMesh", chainsaw, "FileMesh", "2766469", "184182370", VT(1.3, 1.3, 1.3), VT(0, 0 * Player_Size, 0))
local chainsawoverlay = CreatePart(3, Weapon, "SmoothPlastic", 0, 1, "Really red", "Handle", VT(1.2*Player_Size,1.2*Player_Size,5*Player_Size))
local axeweld = CreateWeldOrSnapOrMotor("Weld", HandlePart, chainsawoverlay, HandlePart, CF(0 * Player_Size, 0 * Player_Size, 1.6 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), CF(0, 0, 0))
local HandleMesh = CreateMesh("SpecialMesh", chainsawoverlay, "FileMesh", "2766469", "", VT(1.4, 1.6, 1.35), VT(0, 0 * Player_Size, 0))

if Player_Size ~= 1 then
	for _, v in pairs (Weapon:GetChildren()) do
		if v.ClassName == "Motor" or v.ClassName == "Weld" or v.ClassName == "Snap" then
			local p1 = v.Part1
			v.Part1 = nil
			local cf1, cf2, cf3, cf4, cf5, cf6, cf7, cf8, cf9, cf10, cf11, cf12 = v.C1:components()
			v.C1 = CF(cf1 * Player_Size, cf2 * Player_Size, cf3 * Player_Size, cf4, cf5, cf6, cf7, cf8, cf9, cf10, cf11, cf12)
			v.Part1 = p1
		elseif v.ClassName == "Part" then
			for _, b in pairs (v:GetChildren()) do
				if b.ClassName == "SpecialMesh" or b.ClassName == "BlockMesh" then
					b.Scale = VT(b.Scale.x * Player_Size, b.Scale.y * Player_Size, b.Scale.z * Player_Size)
				end
			end
		end
	end
end

for _, c in pairs(Weapon:GetChildren()) do
	if c.ClassName == "Part" then
		c.CustomPhysicalProperties = PhysicalProperties.new(0, 0, 0, 0, 0)
	end
end

Weapon.Parent = Character

Humanoid.Died:connect(function()
	ATTACK = true
end)

print(Class_Name.." loaded.")

--//=================================\\
--\\=================================//


--//=================================\\
--||			WEAPON GUI
--\\=================================//

local MANABAR = CreateFrame(WEAPONGUI, Mana_Bar_Background_Transparency, 2, UD2(0.23, 0, 0.82, 0), UD2(0.26, 0, 0, 0), C3(Custom_Colors.Custom_Color_8.r, Custom_Colors.Custom_Color_8.g, Custom_Colors.Custom_Color_8.b), C3(0, 0, 0),"Mana Bar") 
local MANACOVER = CreateFrame(MANABAR, 0, 2, UD2(0, 0, 0, 0), UD2(0, 0, 1, 0), C3(Custom_Colors.Custom_Color_5.r, Custom_Colors.Custom_Color_5.g, Custom_Colors.Custom_Color_5.b), C3(0, 0, 0),"Mana Cover")
local MANATEXT = CreateLabel(MANABAR, Mana_Name.." ["..FLOOR(Mana.Value).."]", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Mana Text")

local HEALTHBAR = CreateFrame(WEAPONGUI, Health_Bar_Background_Transparency, 2, UD2(0.5, 0, 0.82, 0), UD2(0.26, 0, 0, 0), C3(Custom_Colors.Custom_Color_11.r, Custom_Colors.Custom_Color_11.g, Custom_Colors.Custom_Color_11.b), C3(0, 0, 0), "Health Bar")
local HEALTHCOVER = CreateFrame(HEALTHBAR, 0, 2,UD2(0, 0, 0, 0), UD2(0, 0, 1, 0), C3(Custom_Colors.Custom_Color_6.r, Custom_Colors.Custom_Color_6.g, Custom_Colors.Custom_Color_6.b), C3(0, 0, 0), "Health Cover")
local HEALTHTEXT = CreateLabel(HEALTHBAR, "Health ["..FLOOR(Humanoid.Health).."]", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Health Text")

local STUNFRAME = CreateFrame(nil, Stun_Bar_Background_Transparency, 2, UD2(0.5, 0, 0.78, 0),UD2(0.26, 0, 0, 0),C3(Custom_Colors.Custom_Color_10.r, Custom_Colors.Custom_Color_10.g, Custom_Colors.Custom_Color_10.b), C3(0, 0, 0), "Stun Frame")
local STUNBAR = CreateFrame(STUNFRAME, 0, 2, UD2(0, 0, 0, 0),UD2(0, 0, 1, 0),C3(Custom_Colors.Custom_Color_7.r, Custom_Colors.Custom_Color_7.g, Custom_Colors.Custom_Color_7.b), C3(0, 0, 0), "Stun Bar")
local STUNTEXT = CreateLabel(STUNFRAME, "Stun ["..FLOOR(StunValue.Value).."]", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Stun Text")

local SECONDARYMANABAR = CreateFrame(nil, Secondary_Mana_Bar_Background_Transparency, 2, UD2(0.23, 0, 0.78, 0), UD2(0.26, 0, 0, 0), C3(Custom_Colors.Custom_Color_9.r, Custom_Colors.Custom_Color_9.g, Custom_Colors.Custom_Color_9.b), C3(0, 0, 0),"Secondary Mana Bar") 
local SECONDARYMANACOVER = CreateFrame(SECONDARYMANABAR, 0, 2, UD2(0, 0, 0, 0), UD2(0, 0, 1, 0), C3(Custom_Colors.Custom_Color_4.r, Custom_Colors.Custom_Color_4.g, Custom_Colors.Custom_Color_4.b), C3(0, 0, 0),"Secondary Mana Cover")
local SECONDARYMANATEXT = CreateLabel(SECONDARYMANABAR, Secondary_Mana_Name.." ["..FLOOR(SecondaryMana.Value).."]", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Secondary Mana Text")

local DEFENSEFRAME = CreateFrame(nil, Stat_Background_Transparency, 2, UD2(0.23, 0, Stat_Offset, 0), UD2(0.075, 0, 0, 0), C3(100 / 255, 100 / 255, 255 / 255), C3(0, 0, 0),"Defense Frame")
local DEFENSETEXT = CreateLabel(DEFENSEFRAME, "Defense ["..(Defense.Value * 100).."%]", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Defense Text")

local DAMAGEFRAME = CreateFrame(nil, Stat_Background_Transparency, 2, UD2(0.456, 0, Stat_Offset, 0), UD2(0.075, 0, 0, 0), C3(255 / 255, 100 / 255, 100 / 255), C3(0, 0, 0),"Damage Frame")
local DAMAGETEXT = CreateLabel(DAMAGEFRAME, "Damage ["..(Damage.Value * 100).."%]", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Damage Text")

local MOVEMENTFRAME = CreateFrame(nil, Stat_Background_Transparency, 2, UD2(0.685, 0, Stat_Offset, 0), UD2(0.075, 0, 0, 0), C3(100 / 255, 255 / 255, 100 / 255), C3(0, 0, 0),"Movement Frame")
local MOVEMENTTEXT = CreateLabel(MOVEMENTFRAME, "Movement ["..(Movement.Value * 100).."%]", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Movement Text")

local SKILL1FRAME = CreateFrame(nil, Ability_Background_Transparency, 2, UD2(0.23, 0, 0.86, 0), UD2(0.26, 0, 0, 0), C3(Custom_Colors.Custom_Color_12.r, Custom_Colors.Custom_Color_12.g, Custom_Colors.Custom_Color_12.b), C3(0, 0, 0), "Skill 1 Frame")
local SKILL2FRAME = CreateFrame(nil, Ability_Background_Transparency, 2, UD2(0.50, 0, 0.86, 0), UD2(0.26, 0, 0, 0), C3(Custom_Colors.Custom_Color_12.r, Custom_Colors.Custom_Color_12.g, Custom_Colors.Custom_Color_12.b), C3(0, 0, 0), "Skill 2 Frame")
local SKILL3FRAME = CreateFrame(nil, Ability_Background_Transparency, 2, UD2(0.23, 0, 0.93, 0), UD2(0.26, 0, 0, 0), C3(Custom_Colors.Custom_Color_12.r, Custom_Colors.Custom_Color_12.g, Custom_Colors.Custom_Color_12.b), C3(0, 0, 0), "Skill 3 Frame")
local SKILL4FRAME = CreateFrame(nil, Ability_Background_Transparency, 2, UD2(0.50, 0, 0.93, 0), UD2(0.26, 0, 0, 0), C3(Custom_Colors.Custom_Color_12.r, Custom_Colors.Custom_Color_12.g, Custom_Colors.Custom_Color_12.b), C3(0, 0, 0), "Skill 4 Frame")

local SKILL1BAR = CreateFrame(SKILL1FRAME, 0, 2, UD2(0, 0, 0, 0), UD2(0, 0, 1, 0), C3(Custom_Colors.Custom_Color_3.r, Custom_Colors.Custom_Color_3.g, Custom_Colors.Custom_Color_3.b), C3(0, 0, 0), "Skill 1 Bar")
local SKILL2BAR = CreateFrame(SKILL2FRAME, 0, 2, UD2(0, 0, 0, 0), UD2(0, 0, 1, 0), C3(Custom_Colors.Custom_Color_3.r, Custom_Colors.Custom_Color_3.g, Custom_Colors.Custom_Color_3.b), C3(0, 0, 0), "Skill 2 Bar")
local SKILL3BAR = CreateFrame(SKILL3FRAME, 0, 2, UD2(0, 0, 0, 0), UD2(0, 0, 1, 0), C3(Custom_Colors.Custom_Color_3.r, Custom_Colors.Custom_Color_3.g, Custom_Colors.Custom_Color_3.b), C3(0, 0, 0), "Skill 3 Bar")
local SKILL4BAR = CreateFrame(SKILL4FRAME, 0, 2, UD2(0, 0, 0, 0), UD2(0, 0, 1, 0), C3(Custom_Colors.Custom_Color_3.r, Custom_Colors.Custom_Color_3.g, Custom_Colors.Custom_Color_3.b), C3(0, 0, 0), "Skill 4 Bar")

local SKILL1TEXT = CreateLabel(SKILL1FRAME, "[Z] Ability 1", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Text 1")
local SKILL2TEXT = CreateLabel(SKILL2FRAME, "[X] Ability 2", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Text 2")
local SKILL3TEXT = CreateLabel(SKILL3FRAME, "[C] Ability 3", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Text 3")
local SKILL4TEXT = CreateLabel(SKILL4FRAME, "[V] Ability 4", C3(1, 1, 1), "Size32", "Legacy", 1, 2, 1, "Text 4")

if Enable_Gui == true then
	WEAPONGUI.Parent = PlayerGui
end

if Enable_Stats == true and Show_Stats == true then
	DEFENSEFRAME.Parent = WEAPONGUI
	DAMAGEFRAME.Parent = WEAPONGUI
	MOVEMENTFRAME.Parent = WEAPONGUI
end

if Enable_Secondary_Bar == true then
	SECONDARYMANABAR.Parent = WEAPONGUI
end

if Enable_Abilities == true then
	SKILL1FRAME.Parent = WEAPONGUI
	SKILL2FRAME.Parent = WEAPONGUI
	SKILL3FRAME.Parent = WEAPONGUI
	SKILL4FRAME.Parent = WEAPONGUI
end

if Enable_Stun == true then
	STUNFRAME.Parent = WEAPONGUI
end

function UpdateGUI()
	MANABAR:TweenSize(UD2(0.26, 0, 0.03, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
	MANACOVER:TweenSize(UD2(1 * (Mana.Value / Max_Mana), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
	MANATEXT.Text = Mana_Name.." ["..FLOOR(Mana.Value).."]"
	HEALTHBAR:TweenSize(UD2(0.26, 0, 0.03, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
	HEALTHCOVER:TweenSize(UD2(1 * (Humanoid.Health / Humanoid.MaxHealth), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
	HEALTHTEXT.Text = "Health ["..FLOOR(Humanoid.Health).."]"
	if Enable_Abilities == true then
		SKILL1FRAME:TweenSize(UD2(0.26, 0, 0.06, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SKILL2FRAME:TweenSize(UD2(0.26, 0, 0.06, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SKILL3FRAME:TweenSize(UD2(0.26, 0, 0.06, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SKILL4FRAME:TweenSize(UD2(0.26, 0, 0.06, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SKILL1BAR:TweenSize(UD2(1 * (CO1 / Cooldown_1), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SKILL2BAR:TweenSize(UD2(1 * (CO2 / Cooldown_2), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SKILL3BAR:TweenSize(UD2(1 * (CO3 / Cooldown_3), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SKILL4BAR:TweenSize(UD2(1 * (CO4 / Cooldown_4), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
	end
	if Enable_Stats == true and Show_Stats == true then
		DEFENSEFRAME:TweenSize(UD2(0.075, 0, 0.03), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		DEFENSETEXT.Text = "Defense ["..(Defense.Value * 100).."%]"
		DAMAGEFRAME:TweenSize(UD2(0.075, 0, 0.03), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		DAMAGETEXT.Text = "Damage ["..(Damage.Value * 100).."%]"
		MOVEMENTFRAME:TweenSize(UD2(0.075, 0, 0.03), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		MOVEMENTTEXT.Text = "Movement ["..(Movement.Value * 100).."%]"
	end
	if Enable_Stun == true then
		STUNFRAME:TweenSize(UD2(0.26, 0, 0.03, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		STUNBAR:TweenSize(UD2(1 * (StunValue.Value / Max_Stun), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		STUNTEXT.Text = "Stun ["..FLOOR(StunValue.Value).."]"
	end
	if Enable_Secondary_Bar == true then
		SECONDARYMANABAR:TweenSize(UD2(0.26, 0, 0.03, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SECONDARYMANACOVER:TweenSize(UD2(1 * (SecondaryMana.Value / Max_Secondary_Mana), 0, 1, 0), "Out", "Quad", Menu_Update_Speed, Constant_Update)
		SECONDARYMANATEXT.Text = Secondary_Mana_Name.." ["..FLOOR(SecondaryMana.Value).."]"
	end
end

if Enable_Gui == true then
	UpdateGUI()
	for _, v in pairs (WEAPONGUI:GetChildren()) do
		if v.ClassName == "Frame" then
			for _, b in pairs (v:GetChildren()) do
				if b.ClassName == "TextLabel" then
					coroutine.resume(coroutine.create(function(THETEXTLABEL)
						wait(Menu_Update_Speed)
						for i = 1, 0, -0.1 do
							Swait()
							THETEXTLABEL.TextTransparency = i
							THETEXTLABEL.TextStrokeTransparency = i
							end
						THETEXTLABEL.TextTransparency = 0
						THETEXTLABEL.TextStrokeTransparency = 0
					end), b)
				end
			end
		end
	end
end

--//=================================\\
--\\=================================//





--//=================================\\
--||	     SKILL FUNCTIONS
--\\=================================//

function UpdateSkillsAndStuff()
	if Mana_Regen_Mode == "1" then
		if Mana.Value >= Max_Mana then
			Mana.Value = Max_Mana
		elseif Mana.Value < 0 then
			Mana.Value = 0
		else
			if MANADELAYNUMBER <= Mana_Wait then
				MANADELAYNUMBER = MANADELAYNUMBER + 1
			else
				MANADELAYNUMBER = 0
				Mana.Value = Mana.Value + Recover_Mana
			end
		end
	elseif Mana_Regen_Mode == "2" then
		if Mana.Value <= Max_Mana then
			Mana.Value = Mana.Value + (Recover_Mana / 30) / Animation_Speed
		elseif Mana.Value >= Max_Mana then
			Mana.Value = Max_Mana
		elseif Mana.Value < 0 then
			Mana.Value = 0
		end
	end
	if Enable_Secondary_Bar == true then
		if Secondary_Mana_Regen_Mode == "1" then
			if SecondaryMana.Value >= Max_Secondary_Mana then
				SecondaryMana.Value = Max_Secondary_Mana
			elseif SecondaryMana.Value < 0 then
				SecondaryMana.Value = 0
			else
				if SECONDARYMANADELAYNUMBER <= Secondary_Mana_Wait then
					SECONDARYMANADELAYNUMBER = SECONDARYMANADELAYNUMBER + 1
				else
					SECONDARYMANADELAYNUMBER = 0
					SecondaryMana.Value = SecondaryMana.Value + Recover_Secondary_Mana
				end
			end
		elseif Secondary_Mana_Regen_Mode == "2" then
			if SecondaryMana.Value <= Max_Secondary_Mana then
				SecondaryMana.Value = SecondaryMana.Value + (Recover_Secondary_Mana / 30) / Animation_Speed
			elseif SecondaryMana.Value >= Max_Secondary_Mana then
				SecondaryMana.Value = Max_Secondary_Mana
			elseif SecondaryMana.Value < 0 then
				SecondaryMana.Value = 0
			end
		end
	else
		SecondaryMana.Value = 0
	end
	if Enable_Stun == true then
		if Stun_Lose_Mode == "1" then
			if StunValue.Value > Max_Stun then
				StunValue.Value = Max_Stun
			elseif StunValue.Value <= 0 then
				StunValue.Value = 0
			else
				if STUNDELAYNUMBER <= Stun_Wait then
					STUNDELAYNUMBER = STUNDELAYNUMBER + 1
				else
					STUNDELAYNUMBER = 0
					StunValue.Value = StunValue.Value - Lose_Stun
				end
			end
		elseif Stun_Lose_Mode == "2" then
			if StunValue.Value <= Max_Stun and StunValue.Value > 0 then
				StunValue.Value = StunValue.Value - (Lose_Stun / 30) / Animation_Speed
			elseif StunValue.Value > Max_Stun then
				StunValue.Value = Max_Stun
			elseif StunValue.Value <= 0 then
				StunValue.Value = 0
			end
		end
	else
		StunValue.Value = 0
	end
	if Enable_Abilities == true then
		if CO1 <= Cooldown_1 then
			CO1 = CO1 + (1 / 30) / Animation_Speed
		elseif CO1 >= Cooldown_1 then
			CO1 = Cooldown_1
		end
		if CO2 <= Cooldown_2 then
			CO2 = CO2 + (1 / 30) / Animation_Speed
		elseif CO2 >= Cooldown_2 then
			CO2 = Cooldown_2
		end
		if CO3 <= Cooldown_3 then
			CO3 = CO3 + (1 / 30) / Animation_Speed
		elseif CO3 >= Cooldown_3 then
			CO3 = Cooldown_3
		end
		if CO4 <= Cooldown_4 then
			CO4 = CO4 + (1 / 30) / Animation_Speed
		elseif CO4 >= Cooldown_4 then
			CO4 = Cooldown_4
		end
	end
end

--//=================================\\
--\\=================================//





--//=================================\\
--||	ATTACK FUNCTIONS AND STUFF
--\\=================================//

local asd = Instance.new("ParticleEmitter")
asd.Color = ColorSequence.new(Color3.new(1, 0, 0), Color3.new(.5, 0, 0))
asd.LightEmission = .1
asd.Size = NumberSequence.new(0.2)
asd.Texture = "http://www.roblox.com/asset/?ID=291880914"
aaa = NumberSequence.new({NumberSequenceKeypoint.new(0, 0.2),NumberSequenceKeypoint.new(1, 5)})
bbb = NumberSequence.new({NumberSequenceKeypoint.new(0, 1),NumberSequenceKeypoint.new(0.0636, 0), NumberSequenceKeypoint.new(1, 1)})
asd.Transparency = bbb
asd.Size = aaa
asd.ZOffset = .9
asd.Acceleration = Vector3.new(0, -5, 0)
asd.LockedToPart = false
asd.EmissionDirection = "Back"
asd.Lifetime = NumberRange.new(1, 2)
asd.Rotation = NumberRange.new(-100, 100)
asd.RotSpeed = NumberRange.new(-100, 100)
asd.Speed = NumberRange.new(2)
asd.Enabled = false
asd.VelocitySpread = 10000

function getbloody(victim,amount)
local prtcl = asd:Clone()
prtcl.Parent = victim
prtcl:Emit(amount)
end

function enablechainsaw()
	CHAINSAWIDLE:Stop()
	REV:Play()
	chainsawoverlay.Transparency = 0.5
end

function disablechainsaw()
	CHAINSAWIDLE:Play()
	REV:Stop()
	chainsawoverlay.Transparency = 1
end

function chop(victim)
	if victim.Parent:FindFirstChild("Humanoid") then
		getbloody(victim,1)
		local human = victim.Parent.Humanoid
		CreateSound(HITPLAYERSOUNDS[MRANDOM(1, #HITPLAYERSOUNDS)], victim, 1, (math.random(8,12)/10))
		if victim.Parent:FindFirstChild("Torso") and human.Health ~= 0 or victim.Parent:FindFirstChild("UpperTorso") and human.Health ~= 0 then
			local torso = victim.Parent:FindFirstChild("Torso") or victim.Parent:FindFirstChild("UpperTorso")
			getbloody(torso,1)
			human.Health = 0
		end
		if human.Health == 0 then
			if FRESHMEAT.Playing == false then
				FRESHMEAT:Play()
			end
		end
	end
end

function BackFromTheDead()
	Humanoid.WalkSpeed = 0
	RootPart.Anchored = true
	disablechainsaw()
	CHAINSAWIDLE:Stop()
	EQUIPPED = false
	sick:Pause()
	getbloody(Torso,35)
	for i = 1, 3 do
		CreateSound(HITPLAYERSOUNDS[MRANDOM(1, #HITPLAYERSOUNDS)], Torso, 1, (math.random(8,12)/10))
	end
	local Animation_Speed2 = 4
	for i = 0, 1, 0.3 / Animation_Speed do
		Swait()
		RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, -0.05 * Player_Size) * ANGLES(RAD(15), RAD(0), RAD(-150)), 0.3 / Animation_Speed)
		Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(-10), RAD(0), RAD(-20)), 0.3 / Animation_Speed)
		RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(30), RAD(0), RAD(40)) * RIGHTSHOULDERC0, 0.3 / Animation_Speed)
		LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-20), RAD(0), RAD(-50)) * LEFTSHOULDERC0, 0.3 / Animation_Speed)
		RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(85), RAD(0)) * ANGLES(RAD(-15), RAD(0), RAD(30)), 0.3 / Animation_Speed)
		LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-80), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(20)), 0.3 / Animation_Speed)
	end
	for i = 0, 1, 0.3 / Animation_Speed do
		Swait()
		RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, -0.05 * Player_Size) * ANGLES(RAD(45), RAD(0), RAD(-180)), 0.4 / Animation_Speed)
		Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(-15), RAD(0), RAD(-30)), 0.4 / Animation_Speed)
		RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(30), RAD(0), RAD(40)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed)
		LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-20), RAD(0), RAD(-50)) * LEFTSHOULDERC0, 0.4 / Animation_Speed)
		RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(85), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(15)), 0.4 / Animation_Speed)
		LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-80), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(50)), 0.4 / Animation_Speed)
	end
	for i = 0, 1, 0.3 / Animation_Speed do
		Swait()
		RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, -0.3 * Player_Size) * ANGLES(RAD(75), RAD(0), RAD(-180)), 0.4 / Animation_Speed)
		Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(-15), RAD(0), RAD(-60)), 0.4 / Animation_Speed)
		RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(20), RAD(0), RAD(70)) * ANGLES(RAD(0), RAD(30), RAD(0)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed)
		LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-10), RAD(0), RAD(-80)) * ANGLES(RAD(0), RAD(-40), RAD(0)) * LEFTSHOULDERC0, 0.4 / Animation_Speed)
		RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(85), RAD(0)) * ANGLES(RAD(-15), RAD(0), RAD(10)), 0.4 / Animation_Speed)
		LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-80), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(80)), 0.4 / Animation_Speed)
	end
	for i = 1, 50 * Animation_Speed do
		Swait()
		RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, -2.5 * Player_Size) * ANGLES(RAD(90), RAD(0), RAD(-180)), 0.3 / Animation_Speed)
		Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(0), RAD(0), RAD(-90)), 0.3 / Animation_Speed)
		RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(90), RAD(-10), RAD(90)) * RIGHTSHOULDERC0, 0.3 / Animation_Speed)
		LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-90), RAD(0), RAD(-90)) * LEFTSHOULDERC0, 0.3 / Animation_Speed)
		RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0.2 * Player_Size) * ANGLES(RAD(0), RAD(70), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(0)), 0.3 / Animation_Speed)
		LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-80), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(0)), 0.3 / Animation_Speed)
	end
	local bloodpit = Instance.new("Part",Effects)
	bloodpit.Size = Vector3.new(14,0.2,14)
	bloodpit.CFrame = CFrame.new(RootPart.Position.X,RootPart.Position.Y-3,RootPart.Position.Z)
	bloodpit.Anchored = true
	bloodpit.CanCollide = false
	bloodpit.Material = "Neon"
	bloodpit.BrickColor = BrickColor.new("Really red")
	local cyl = Instance.new("CylinderMesh",bloodpit)
	local Animation_Speed2 = 15
	bloodpit.Transparency = 1
	CHAINSAWSTRIKE:Play()
	for i = 1, 10 do
		Swait(5)
		bloodpit.Transparency = bloodpit.Transparency - 0.1
	end
	for i = 1, 20 * Animation_Speed do
		Swait()
		RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, -5.5 * Player_Size) * ANGLES(RAD(90), RAD(0), RAD(-180)), 0.3 / Animation_Speed)
		Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(0), RAD(0), RAD(-90)), 0.3 / Animation_Speed)
		RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(90), RAD(-10), RAD(90)) * RIGHTSHOULDERC0, 0.3 / Animation_Speed)
		LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-90), RAD(0), RAD(-90)) * LEFTSHOULDERC0, 0.3 / Animation_Speed)
		RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0.2 * Player_Size) * ANGLES(RAD(0), RAD(70), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(0)), 0.3 / Animation_Speed)
		LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-80), RAD(0)) * ANGLES(RAD(-10), RAD(0), RAD(0)), 0.3 / Animation_Speed)
	end
	Character.Part:remove()
	demon = true
	createaccessory(Head,"http://www.roblox.com/asset/?id=1271547","rbxassetid://99174105",VT(1.05, 1.05, 1.05),VT(0, 1, 0),BrickColor.new"Really black")
	for i=0, 1, 0.1 / Animation_Speed2 do
		Swait()
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, -15 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
		    RightShoulder.C0 = Clerp(RightShoulder.C0, CF(0.45 * Player_Size, 0.5 * Player_Size, -1 * Player_Size) * ANGLES(RAD(70), RAD(0), RAD(-70)) * ANGLES(RAD(20), RAD(25), RAD(-15)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed2)
		    LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1 * Player_Size, 0.2 * Player_Size, -0.5 * Player_Size) * ANGLES(RAD(25), RAD(0), RAD(55)) * LEFTSHOULDERC0, 0.4 / Animation_Speed2)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
		if StaggerHit.Value == true or Stagger.Value == true or Stun.Value == true then
			break
		end
	end
	Taunt()
	for i=0, 2, 0.1 / Animation_Speed do
		Swait()
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		    RightShoulder.C0 = Clerp(RightShoulder.C0, CF(0.45 * Player_Size, 0.5 * Player_Size, -1 * Player_Size) * ANGLES(RAD(70), RAD(0), RAD(-70)) * ANGLES(RAD(20), RAD(25), RAD(-15)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed)
		    LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1 * Player_Size, 0.2 * Player_Size, -0.5 * Player_Size) * ANGLES(RAD(25), RAD(0), RAD(55)) * LEFTSHOULDERC0, 0.4 / Animation_Speed)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		if StaggerHit.Value == true or Stagger.Value == true or Stun.Value == true then
			break
		end
	end
	for i = 1, 10 do
		Swait(5)
		bloodpit.Transparency = bloodpit.Transparency + 0.1
	end
	BLCF = nil
	SCFR = nil
	sick:Play()
	Humanoid.WalkSpeed = 35
	RootPart.Anchored = false
	CHAINSAWIDLE:Play()
	EQUIPPED = true
	ATTACK = false
end

function Attack1()
	ATTACK = true
	enablechainsaw()
	if demon == false then
		Humanoid.WalkSpeed = 15
	elseif demon == true then
		Humanoid.WalkSpeed = 25
	end
	local Animation_Speed2 = 0.5
	for i=0, 1, 0.1 / Animation_Speed2 do
		Swait()
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1 * Player_Size, 0.35 * Player_Size, -0.9 * Player_Size) * ANGLES(RAD(17), RAD(0), RAD(-35)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed2)
			LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1 * Player_Size, 0.35 * Player_Size, -0.8 * Player_Size) * ANGLES(RAD(32), RAD(0), RAD(35)) * LEFTSHOULDERC0, 0.4 / Animation_Speed2)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
	end
	local hit = chainsaw.Touched:connect(function(hit)
		chop(hit)
	end)
	repeat Swait() until HOLD == false
	if demon == false then
		Humanoid.WalkSpeed = 20
	elseif demon == true then
		Humanoid.WalkSpeed = 35
	end
	hit:disconnect()
	disablechainsaw()
	BLCF = nil
	SCFR = nil
	ATTACK = false
end

Humanoid.HealthChanged:connect(function()
	if Humanoid.Health == 0 and INTRODONE == true then
		Humanoid.MaxHealth = "inf"
		Humanoid.Health = "inf"
		if EQUIPPED == true and hasdied == false then
			hasdied = true
			BackFromTheDead()
		end
	end
end)


function Intro()
	ANIMATE.Parent = nil
		local IDLEANIMATION = Humanoid:LoadAnimation(ROBLOXIDLEANIMATION)
		IDLEANIMATION:Play()
	ATTACK = true
	RootPart.Anchored = true
	Humanoid.WalkSpeed = 0
	for i=0, 1, 0.1 / Animation_Speed do
		Swait()
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		    RightShoulder.C0 = Clerp(RightShoulder.C0, CF(0.45 * Player_Size, 0.5 * Player_Size, -1 * Player_Size) * ANGLES(RAD(70), RAD(0), RAD(-70)) * ANGLES(RAD(20), RAD(25), RAD(-15)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed)
		    LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1 * Player_Size, 0.2 * Player_Size, -0.5 * Player_Size) * ANGLES(RAD(25), RAD(0), RAD(55)) * LEFTSHOULDERC0, 0.4 / Animation_Speed)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		if StaggerHit.Value == true or Stagger.Value == true or Stun.Value == true then
			break
		end
	end
	local bloodpit = Instance.new("Part",Effects)
	bloodpit.Size = Vector3.new(8,0.2,8)
	bloodpit.CFrame = CFrame.new(RootPart.Position.X,RootPart.Position.Y-3,RootPart.Position.Z)
	bloodpit.Anchored = true
	bloodpit.CanCollide = false
	bloodpit.Material = "Neon"
	bloodpit.BrickColor = BrickColor.new("Really red")
	local cyl = Instance.new("CylinderMesh",bloodpit)
	local Animation_Speed2 = 15
	bloodpit.Transparency = 1
	CHAINSAWSTRIKE:Play()
	for i = 1, 10 do
		Swait(5)
		bloodpit.Transparency = bloodpit.Transparency - 0.1
	end
	for i=0, 1, 0.1 / Animation_Speed2 do
		Swait()
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, -15 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
		    RightShoulder.C0 = Clerp(RightShoulder.C0, CF(0.45 * Player_Size, 0.5 * Player_Size, -1 * Player_Size) * ANGLES(RAD(70), RAD(0), RAD(-70)) * ANGLES(RAD(20), RAD(25), RAD(-15)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed2)
		    LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1 * Player_Size, 0.2 * Player_Size, -0.5 * Player_Size) * ANGLES(RAD(25), RAD(0), RAD(55)) * LEFTSHOULDERC0, 0.4 / Animation_Speed2)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed2)
		if StaggerHit.Value == true or Stagger.Value == true or Stun.Value == true then
			break
		end
	end
	Taunt()
	Swait(15)
	Head.face:remove()
	createaccessory(Head,"http://www.roblox.com/asset/?id=62146989","rbxassetid://145633085",VT(1.05, 1.05, 1.05),VT(0, 0.1, -0.05),BrickColor.new"Really black")
	local blood = Instance.new("Decal",Torso)
	blood.Texture = "http://www.roblox.com/asset/?id=116830967"
	createbodypart("Eye","Maroon",Head,VT(0.2, 0.15, -0.55),VT(5,3,3))
	createbodypart("Eye","Maroon",Head,VT(-0.2, 0.15, -0.55),VT(5,3,3))
	EQUIPPED = true
	chainsaw.CanCollide = true
	CHAINSAWIDLE:Play()
	for i = 1, 2 do
	for i=0, 1, 0.1 / Animation_Speed do
		Swait()
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		    RightShoulder.C0 = Clerp(RightShoulder.C0, CF(0.45 * Player_Size, 0.5 * Player_Size, -1 * Player_Size) * ANGLES(RAD(70), RAD(0), RAD(-70)) * ANGLES(RAD(20), RAD(25), RAD(-15)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed)
		    LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1 * Player_Size, 0.2 * Player_Size, -0.5 * Player_Size) * ANGLES(RAD(25), RAD(0), RAD(55)) * LEFTSHOULDERC0, 0.4 / Animation_Speed)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		if StaggerHit.Value == true or Stagger.Value == true or Stun.Value == true then
			break
		end
	end
	end
	sick:play()
	for i = 1, 10 do
		Swait(5)
		bloodpit.Transparency = bloodpit.Transparency + 0.1
	end
	RootPart.Anchored = false
	bloodpit:remove()
	Humanoid.WalkSpeed = 20
	BLCF = nil
	SCFR = nil
	INTRODONE = true
	ATTACK = false
end

--//=================================\\
--\\=================================//



--//=================================\\
--||	  ASSIGN THINGS TO KEYS
--\\=================================//

Humanoid.Changed:connect(function(Jump)
	if Jump == "Jump" and (Disable_Jump == true or DISABLEJUMPING == true) then
		Humanoid.Jump = false
	end
end)

function MouseDown(Mouse)
	if ATTACK == true or EQUIPPED == false then
		return
	end
	HOLD = true
		Attack1()
	coroutine.resume(coroutine.create(function()
		for i=1, 50 do
			if ATTACK == false then
				Swait()
			end
		end
		if ATTACK == false then
			COMBO = 1
		end
	end))
end

function MouseUp(Mouse)
HOLD = false
end

function Taunt()
	if Taunt1.Playing == false and Taunt2.Playing == false and Taunt3.Playing == false and Taunt4.Playing == false then
		local udied = TAUNTS[math.random(1, #TAUNTS)]
		udied:Play()
	end
end

function KeyDown(Key)
	KEYHOLD = true
	if Key == "e" and EQUIPPED == true and ATTACK == false then
	end
	if Key == "f" and EQUIPPED == false and ATTACK == false then
		Intro()
	end
	if Key == "t" and EQUIPPED == true and ATTACK == false then
		Taunt()
	end
	if Player.UserId == owner
		if Key == "q" then
			Mana.Value = Max_Mana
			SecondaryMana.Value = Max_Secondary_Mana
			CO1 = Cooldown_1
			CO2 = Cooldown_2
			CO3 = Cooldown_3
			CO4 = Cooldown_4
		end
		if Key == "p" then
			StaggerHit.Value = true
		end
		if Key == "[" then
			Stagger.Value = true
		end
		if Key == "]" then
			Stun.Value = true
		end
	end
end

function KeyUp(Key)
	KEYHOLD = false
end

	Mouse.Button1Down:connect(function(NEWKEY)
		MouseDown(NEWKEY)
	end)
	Mouse.Button1Up:connect(function(NEWKEY)
		MouseUp(NEWKEY)
	end)
	Mouse.KeyDown:connect(function(NEWKEY)
		KeyDown(NEWKEY)
	end)
	Mouse.KeyUp:connect(function(NEWKEY)
		KeyUp(NEWKEY)
	end)


--//=================================\\
--\\=================================//





--//=================================\\
--||	WRAP THE WHOLE SCRIPT UP
--\\=================================//

while true do
	Swait()
	SINE = SINE + CHANGE
	local TORSOVELOCITY = (RootPart.Velocity * VT(1, 0, 1)).magnitude
	local TORSOVERTICALVELOCITY = RootPart.Velocity.y
	local LV = Torso.CFrame:pointToObjectSpace(Torso.Velocity - Torso.Position)
	local HITFLOOR = Raycast(RootPart.Position, (CF(RootPart.Position, RootPart.Position + VT(0, -1, 0))).lookVector, 4 * Player_Size, Character)
	local WALKSPEEDVALUE = 6 / (Humanoid.WalkSpeed / 16)
	if ANIM == "Walk" and EQUIPPED == true and TORSOVELOCITY > 1 then
		RootJoint.C1 = Clerp(RootJoint.C1, ROOTC0 * CF(0, 0, -0.05 * COS(SINE / (WALKSPEEDVALUE / 2)) * Player_Size) * ANGLES(RAD(0), RAD(0) - RootPart.RotVelocity.Y / 75, RAD(0)), 0.1 * (Humanoid.WalkSpeed / 16) / Animation_Speed)
		Neck.C1 = Clerp(Neck.C1, CF(0 * Player_Size, -0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-90), RAD(0), RAD(180)) * ANGLES(RAD(2.5 * SIN(SINE / (WALKSPEEDVALUE / 2))), RAD(0), RAD(0) - Head.RotVelocity.Y / 30), 0.2 * (Humanoid.WalkSpeed / 16) / Animation_Speed)
		RightHip.C1 = Clerp(RightHip.C1, CF(0.5 * Player_Size, 0.875 * Player_Size - 0.125 * SIN(SINE / WALKSPEEDVALUE) * Player_Size, -0.125 * COS(SINE / WALKSPEEDVALUE) * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0) - RightLeg.RotVelocity.Y / 75, RAD(0), RAD(60 * COS(SINE / WALKSPEEDVALUE))), 0.2 * (Humanoid.WalkSpeed / 16) / Animation_Speed)
		LeftHip.C1 = Clerp(LeftHip.C1, CF(-0.5 * Player_Size, 0.875 * Player_Size + 0.125 * SIN(SINE / WALKSPEEDVALUE) * Player_Size, 0.125 * COS(SINE / WALKSPEEDVALUE) * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0) + LeftLeg.RotVelocity.Y / 75, RAD(0), RAD(60 * COS(SINE / WALKSPEEDVALUE))), 0.2 * (Humanoid.WalkSpeed / 16) / Animation_Speed)
	elseif (ANIM ~= "Walk" and EQUIPPED == true) or (TORSOVELOCITY < 1) then
		RootJoint.C1 = Clerp(RootJoint.C1, ROOTC0 * CF(0, 0, 0) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		Neck.C1 = Clerp(Neck.C1, CF(0 * Player_Size, -0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-90), RAD(0), RAD(180)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		RightHip.C1 = Clerp(RightHip.C1, CF(0.5 * Player_Size, 1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		LeftHip.C1 = Clerp(LeftHip.C1, CF(-0.5 * Player_Size, 1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
	end
	if TORSOVERTICALVELOCITY > 1 and HITFLOOR == nil then
		ANIM = "Jump"
		if EQUIPPED == true and ATTACK == false then
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(-20), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-40), RAD(0), RAD(20)) * RIGHTSHOULDERC0, 0.2 / Animation_Speed)
			LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(-40), RAD(0), RAD(-20)) * LEFTSHOULDERC0, 0.2 / Animation_Speed)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, -0.3 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(-5), RAD(0), RAD(-20)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, -0.3 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(-5), RAD(0), RAD(20)), 0.2 / Animation_Speed)
        end
	elseif TORSOVERTICALVELOCITY < -1 and HITFLOOR == nil then
		ANIM = "Fall"
		if EQUIPPED == true and ATTACK == false then
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(20), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(60)) * RIGHTSHOULDERC0, 0.2 / Animation_Speed)
			LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.5 * Player_Size, 0.5 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(-60)) * LEFTSHOULDERC0, 0.2 / Animation_Speed)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(20)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(10)), 0.2 / Animation_Speed)
		end
	elseif TORSOVELOCITY < 1 and HITFLOOR ~= nil then
		ANIM = "Idle"
		if EQUIPPED == true and ATTACK == false then
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1 * Player_Size, 0.35 * Player_Size, -0.9 * Player_Size) * ANGLES(RAD(17), RAD(35), RAD(-35)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed)
			LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.35 * Player_Size, 0.35 * Player_Size, -0.5 * Player_Size) * ANGLES(RAD(32), RAD(-12), RAD(35)) * LEFTSHOULDERC0, 0.4 / Animation_Speed)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
		end
	elseif TORSOVELOCITY > 1 and HITFLOOR ~= nil then
		ANIM = "Walk"
		WALK = WALK + 1 / Animation_Speed
		if WALK >= 15 - (5 * (Humanoid.WalkSpeed / 16 / Player_Size)) then
			WALK = 0
			if WALKINGANIM == true then
				WALKINGANIM = false
			elseif WALKINGANIM == false then
				WALKINGANIM = true
			end
		end
		if EQUIPPED == true and ATTACK == false then
			RootJoint.C0 = Clerp(RootJoint.C0, ROOTC0 * CF(0 * Player_Size, 0 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			Neck.C0 = Clerp(Neck.C0, NECKC0 * CF(0 * Player_Size, 0 * Player_Size, 0 + ((1 * Player_Size) - 1)) * ANGLES(RAD(10), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			RightShoulder.C0 = Clerp(RightShoulder.C0, CF(1 * Player_Size, 0.35 * Player_Size, -0.9 * Player_Size) * ANGLES(RAD(17), RAD(35), RAD(-35)) * RIGHTSHOULDERC0, 0.4 / Animation_Speed)
			LeftShoulder.C0 = Clerp(LeftShoulder.C0, CF(-1.35 * Player_Size, 0.35 * Player_Size, -0.5 * Player_Size) * ANGLES(RAD(32), RAD(-12), RAD(35)) * LEFTSHOULDERC0, 0.4 / Animation_Speed)
			RightHip.C0 = Clerp(RightHip.C0, CF(1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
			LeftHip.C0 = Clerp(LeftHip.C0, CF(-1 * Player_Size, -1 * Player_Size, 0 * Player_Size) * ANGLES(RAD(0), RAD(-90), RAD(0)) * ANGLES(RAD(0), RAD(0), RAD(0)), 0.2 / Animation_Speed)
	    end
    end
q = Character:GetChildren()
if EQUIPPED == true or demon == true then
chainsaw.Transparency = 0
for u = 1, #q do
	if q[u].ClassName == "Accessory" or q[u].ClassName == "Hat" then
		q[u]:remove()
	elseif q[u].ClassName == "Shirt" and q[u].Name ~= "ChaniacClothes1" then
		q[u]:Destroy()
	elseif q[u].ClassName == "Pants" and q[u].Name ~= "ChaniacClothes2" then
		q[u]:Destroy()
	elseif q[u].ClassName == "CharacterMesh" then
		q[u].OverlayTextureId = "99174105"
	elseif q[u].ClassName == "ShirtGraphic" then
		q[u]:remove()
	elseif q[u].ClassName == "Part" and q[u].Name ~= "HumanoidRootPart" then
		if demon == true then
			q[u].Color = Color3.new(0/255, 0/255, 0/255)
		else
			q[u].Color = Color3.new(255/255, 230/255, 194/255)
		end
	end
end
if Character:FindFirstChild("ChaniacClothes1") == nil then
	local top = Instance.new("Shirt")
	top.ShirtTemplate = "rbxassetid://1164958918"
	top.Parent = Character
	top.Name = "ChaniacClothes1"
end
if Character:FindFirstChild("ChaniacClothes2") == nil then
	local bottom = Instance.new("Pants")
	bottom.PantsTemplate = "rbxassetid://143808031"
	bottom.Parent = Character
	bottom.Name = "ChaniacClothes2"
end
end
if Humanoid.MaxHealth ~= 15000 and hasdied == false then
	Humanoid.MaxHealth = 15000
	Humanoid.Health = 15000
elseif hasdied == true then
	Humanoid.MaxHealth = "inf"
	Humanoid.Health = "inf"
end
end

--//=================================\\
--\\=================================//





--//====================================================\\--
--||			  		 END OF SCRIPT
--\\====================================================//--
