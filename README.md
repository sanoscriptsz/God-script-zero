
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()


Esses trÃªs comandos carregam a biblioteca principal e dois gerenciadores (salvar configuraÃ§Ãµes e gerenciar interface).


2. Criar a Janela Principal:

local Window = Fluent:CreateWindow({
    Title = "Fluent " .. Fluent.Version,
    TabWidth = 160, Size = UDim2.fromOffset(580, 460), Theme = "Dark"
})

Esta parte cria a janela principal da interface com tema escuro e define o tamanho e tÃ­tulo.


3. Adicionar Abas (Tabs):

local Tabs = {
    Main = Window:AddTab({ Title = "Main" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}

Aqui, duas abas sÃ£o adicionadas: Main (principal) e Settings (configuraÃ§Ãµes).


4. Adicionar Elementos na Aba Main:

NotificaÃ§Ã£o:

Fluent:Notify({ Title = "Notification", Content = "This is a notification" })

Exibe uma notificaÃ§Ã£o simples.

ParÃ¡grafo:

Tabs.Main:AddParagraph({ Title = "Paragraph", Content = "This is a paragraph.\nSecond line!" })

Exibe um parÃ¡grafo com texto formatado.

BotÃ£o:

Tabs.Main:AddButton({ Title = "Button", Callback = function() ... end })

Adiciona um botÃ£o que abre um diÃ¡logo com opÃ§Ãµes de confirmaÃ§Ã£o.

Toggle (Alternador):

local Toggle = Tabs.Main:AddToggle("MyToggle", { Title = "Toggle" })
Toggle:OnChanged(function() print(Options.MyToggle.Value) end)

Adiciona um alternador (on/off) que executa uma funÃ§Ã£o ao ser ativado.



5. Outros Elementos:

Slider: Controle deslizante de valores.

Dropdown: Menu suspenso com mÃºltiplas opÃ§Ãµes.

Colorpicker: Seletor de cores com transparÃªncia.

Keybind: Atalho de teclado personalizÃ¡vel.

Input: Campo de texto para inserÃ§Ã£o de valores.



6. Adicionar Funcionalidade dos Add-ons:

SaveManager:SetLibrary(Fluent)
InterfaceManager:SetLibrary(Fluent)

O SaveManager e InterfaceManager sÃ£o integrados Ã  janela Fluent para gerenciar configuraÃ§Ãµes e interfaces.
