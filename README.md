# vsSkins!

> Um pack de skins de bebes/crianças para o FiveM

> Developed by: Vieira's Store

> Framework: vRPex ┃ Creative

# Dependências

> vRP/vRPex

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
    if vRP.hasPermission(user_id,"dono.permissao") then
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

> Creative

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
RegisterCommand("skin",function(source,args,rawCommand)
    local user_id = vRP.getUserId(source)
	if vRP.hasGroup(user_id,"Admin") then
		TriggerClientEvent("skinmenu",args[1],args[2])
		TriggerClientEvent("Notify",source,"amarelo","Setada a skin <b>"..args[2].."</b> no passaporte <b>"..parseInt(args[1]).."</b>.",5000)
    end
end)
```

# Atenção

> Após voce extrair o arquivo vsSkins-main renomear para vsSkins.

> Após colocar uma skin e quizer voltar para skin normal utilizar os comandos:

> Voltar para personagem masculino: /skin id mp_m_freemode_01

> Voltar para personagem feminino: /skin id mp_f_freemode_01

# Preview!

> Para ver o video/preview clicar em cima do play.

<a href="https://www.youtube.com/watch?v=UdtGxifTXbU&t=42s" target="blank">
      <img align="center" src="https://cdn.discordapp.com/attachments/1025184841370714183/1025205129101717565/unknown.png"/>
</a>

# Suporte

> Caso não funcione na sua base chamar: EuNoah#8056 no discord.
