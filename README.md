Add this on top your client side file
```
MenuData = {}
TriggerEvent("murphy_menu:getData",function(call)
    MenuData = call
end)
```
Example:
```
MenuData.CloseAll()
local elements = {
    {
     label = "Test Option",
     value = 'test' ,
     desc = "Press if you want print text",
     image="items/weapon_melee_hammer.png",
     descriptionimages = {
      {
       src = "nui://murphy_menu/html/items/cloth.png",
       text = "Kumaş",
       count = "x1"
      },

      {
       src = "nui://murphy_menu/html/items/woodenplanks.png",
       count = "x5",
       text = "Ahşap"
      }
     },
    },
    {label = "Hop Test", value = 0  ,desc = "Look its so fast" , type = "slider" , min =0 , max =100, hop= 5},
}

local nuifocus = false
MenuData.Open('default', GetCurrentResourceName(), 'test_menu',
{
    title   = 'TestMenu',
    subtext = 'There is a subtext',
    align   = 'top-left',
    elements = elements,
},
function(data, menu)
    if(data.current.value == 'test') then
        print("test")
    end
end,
function(data, menu)
    menu.close()
end,nuifocus)
```

# Credits
Based on redemrp menu base
- https://github.com/ktos93
- https://github.com/ESX-Org
- https://github.com/abdulkadiraktas
- https://github.com/youngsinatra99