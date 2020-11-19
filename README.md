
                                                              Trew HUD UI
                                                               credit:vortisrd
Installation

Extract the .zip or Open the .zip.
-
Place trew_hud_ui in your resources directory.
-
Add start trew_hud_ui to your server.cfg
-
Requirements
es_extended
esx_society
esx_addonaccount
Optional
esx_basicneeds
esx_status
LegacyFuel (it should be started BEFORE the trew_hud_ui)
-
Post Installation
Go to es_extended config.lua and turn Config.EnableHud to false
-
If needed, go to esx_basicneeds main.lua and replace this code

TriggerEvent('esx_status:registerStatus', 'hunger', 1000000, '#CFAD0F', function(status)
	return true
end, function(status)
	status.remove(1000)
end)
TriggerEvent('esx_status:registerStatus', 'thirst', 1000000, '#0C98F1', function(status)
	return true
end, function(status)
	status.remove(750)
end)
for this one

  TriggerEvent('esx_status:registerStatus', 'hunger', 1000000, '#CFAD0F', function(status)
  	return false
  end, function(status)
  	status.remove(1000)
  end)
  TriggerEvent('esx_status:registerStatus', 'thirst', 1000000, '#0C98F1', function(status)
  	return false
  end, function(status)
  	status.remove(750)
  end)
