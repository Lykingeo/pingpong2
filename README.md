# pingpong2
from pygame import *


class GameSprite(sprite.Sprite):
    def __init__(self, player_image, player_x, player_y, player_speed, size_x, size_y)
        super().__init__()
        self

class Player1(GameSprite):
    def update_l(self):
        keys = key.get_pressed()
        if keys[K_w] and self.rect.y > 5:
            self.rect.y -= self.speed
        if keys[K_s] and self.rect.y - 80:
            self.rect.y += self.speed

class Player2(GameSprite):
    def update_r(self):
        keys = key.get_pressed()
        if keys[K_UP] and self.rect.y > 5:
            self.rect.y -= self.speed
        if keys[K_DOWN] and self.rect.y - 80:
            self.rect.y += self.speed

finish = False
clock = time.Clock
FPS = 60

racket1 = Player("racket.png", 30, 200, 4, 50, 150)
racket2 = Player("racket.png", 520, 200, 4, 50, 150)
ball = GameSprite("tenis_ball.png", 200, 200, 4, 50, 50)

font.init()
font = font.Font(None, 35)
lose1 = font.render("PLAYER 1 LOSE", True, (180, 0, 0))
lose2 = font.render("PLAYER 2 LOSE", True, (180, 0, 0))

speed_x = 3
speed_y = 3

while game:
    for i in event.get():
        if e.type == QUIT:
            game = False

    if finish != True:
        window.fill(back)
        

        if  ball.rect.x < 0:
            finish = True
            window.blit(lose1, (200, 200))

        if  ball.rect.x > win_width:
            finish = True
            window.blit(lose2, (200, 200))

        racket1.reset()
        racket2.reset()
        ball.reset()

display.update()
clock.tick(FPS)
