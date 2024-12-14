local button = {}
local message = ""

function love.load()
    
    button.x = 200
    button.y = 150
    button.width = 200
    button.height = 50
    button.color = {0.2, 0.6, 1} -- Blau
end

function love.update(dt)

    if love.mouse.isDown(1) then
        local mx, my = love.mouse.getPosition()
        if mx >= button.x and mx <= button.x + button.width and
           my >= button.y and my <= button.y + button.height then
            message = "Button wurde geklickt!"
        end
    end
end

function love.draw()
    
    love.graphics.setColor(button.color)
    love.graphics.rectangle("fill", button.x, button.y, button.width, button.height)

    love.graphics.setColor(1, 1, 1)  -- Weiß
    love.graphics.printf("Klick mich!", button.x, button.y + button.height / 4, button.width, "center")


    if message ~= "" then
        love.graphics.setColor(1, 1, 1)  -- Weiß
        love.graphics.printf(message, 50, 250, love.graphics.getWidth() - 100, "center")
    end
end
