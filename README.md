RegisterNetEvent('clientPrint')
AddEventHandler('clientPrint', function(message)
    -- Imprimer le message dans la console en jeu
    print("[FxServers Vous remercie Discord.gg/votreDiscord - Tiktok Le votre] " .. message)
end)




------- Removecops

Citizen.CreateThread(function()
  while true do
      Citizen.Wait(375)
      local myCoords = GetEntityCoords(PlayerPedId())
      ClearAreaOfCops(myCoords.x, myCoords.y, myCoords.z, 100.0, 0)
  end
end)

Citizen.CreateThread(function()
  for i = 1, 12 do
      Citizen.InvokeNative(0xDC0F817884CDD856, i, false)
  end
end)

Citizen.CreateThread(function()
  while true do
      Citizen.Wait(300)
     
      if GetPlayerWantedLevel(PlayerId()) ~= 0 then
          SetPlayerWantedLevel(PlayerId(), 0, false)
          SetPlayerWantedLevelNow(PlayerId(), false)
      end
  end
end)

--- Enlever taper avec R 

Citizen.CreateThread(function()
  while true do
      Citizen.Wait(5)
      DisableControlAction(0, 140, true)
  end
end)

--- Enlever Roulades

Citizen.CreateThread(function()
  while true do
      Citizen.Wait(5)
      if IsControlPressed(0, 25)
          then DisableControlAction(0, 22, true)
      end
  end
end)

