# vsSkins!

> Um pack de skins de bebes/crianças para o FiveM

> Developed by: Vieira's Store

> Framework: vRPex ┃ Creative


> Após colocar uma skin e quizer voltar para skin normal utilizar os comandos:

> Voltar para personagem masculino: /skin id mp_m_freemode_01

> Voltar para personagem feminino: /skin id mp_f_freemode_01

# Dependências

VRPEX

```lua
-------------------------------------------------------------------------
-- /SKIN - COLOCAR EM QUALQUER CLIENT.LUA
-------------------------------------------------------------------------
RegisterNetEvent("skinmenu")
AddEventHandler("skinmenu",function(mhash)
    while not HasModelLoaded(mhash) do
        RequestModel(mhash)
        Citizen.Wait(10)
    end

    if HasModelLoaded(mhash) then
        SetPlayerModel(PlayerId(),mhash)
        SetModelAsNoLongerNeeded(mhash)
    end
end)
```


```lua
-------------------------------------------------------------------------
-- /SKIN - COLOCAR EM QUALQUER SERVER.LUA (Obs: Configurar permissão)
-------------------------------------------------------------------------
RegisterCommand('skin',function(source,args,rawCommand)
    local user_id = vRP.getUserId(source)
    if vRP.terPemissao(user_id,"dono.permissao") then
        if parseInt(args[1]) then
            local nplayer = vRP.getUserSource(parseInt(args[1]))
            if nplayer then
                TriggerClientEvent("skinmenu",nplayer,args[2])
                TriggerClientEvent("Notify",source,"sucesso","Voce setou a skin <b>"..args[2].."</b> no passaporte <b>"..parseInt(args[1]).."</b>.")
            end
        end
    end
end)
```

# Preview!

> https://www.youtube.com/watch?v=UdtGxifTXbU&t=67s

> ![image](https://user-images.githubusercontent.com/98975919/185752465-b3bf0074-d8bb-4843-8660-6e07be54a4a2.png)

# Suporte

> Caso não funcione na sua base chamar: EuNoah#8056 no discord.
