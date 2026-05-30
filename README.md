local plrs = game:GetService("Players")
local rs = game:GetService("RunService")
local lp = plrs.LocalPlayer

local function upd()
	local nick = "lnoxodec"
	local c = lp.Character
	if c then
		for _, v in pairs(c:GetDescendants()) do
			if v:IsA("TextLabel") and (v.Text == lp.Name or v.Text == lp.DisplayName or v.Text == "follow") then
				v.Text = nick
			end
		end
	end
	
	local gui = lp:WaitForChild("PlayerGui", 5)
	if gui then
		for _, v in pairs(gui:GetDescendants()) do
			if v:IsA("TextLabel") and (v.Text == lp.Name or v.Text == lp.DisplayName or v.Text == "follow") then
				v.Text = nick
			end
		end
	end
end

rs.RenderStepped:Connect(upd)
