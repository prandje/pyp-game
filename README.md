import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up the game window
width, height = 800, 600
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Your Game Title")

# Set up colors
white = (255, 255, 255)
black = (0, 0, 0)

# Set up the player
player_size = 50
player_x = width // 2 - player_size // 2
player_y = height - 2 * player_size
player_speed = 5

# Main game loop
while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Update player position
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and player_x > 0:
        player_x -= player_speed
    if keys[pygame.K_RIGHT] and player_x < width - player_size:
        player_x += player_speed

    # Draw everything
    screen.fill(white)
    pygame.draw.rect(screen, black, (player_x, player_y, player_size, player_size))

    # Update the display
    pygame.display.flip()

    # Control the game speed
    pygame.time.Clock().tick(30)





 
