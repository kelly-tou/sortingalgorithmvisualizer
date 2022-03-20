import pygame
import sys
from bar import bar_array
from algorithms import *

pygame.init()
display_width = 500
display_height = 300
screen = pygame.display.set_mode((display_width, display_height))
pygame.display.set_caption("Sorting Algorithm Visualizer")

b = input("Input number of bars (max = 80): ")
z = bar_array(int(b)) #max 80

def reset():
	global z
	b = input("Input number of bars: ")
	z = bar_array(int(b))
	
while True:
	screen.fill((2,6,33))
	z.draw(screen)

	font = pygame.font.Font("freesansbold.ttf", 15)
	text = font.render("press b for bubble sort, press i for insertion sort, press q for quick", True, (255,255,255))
	text_rect = text.get_rect()
	text_rect.center=(display_width/2, 20)
	screen.blit(text, text_rect)
	text1 = font.render("sort, press h for heap sort, press r to generate a new bar array", True, (255,255,255))
	text_rect1 = text1.get_rect()
	text_rect1.center=(display_width/2, 40)
	screen.blit(text1, text_rect1)
	
	for event in pygame.event.get():
		if event.type == pygame.QUIT:
			pygame.quit()
			sys.exit()
		if event.type == pygame.KEYDOWN:
			if event.key == pygame.K_b:
				bubble_sort(z, screen)
			elif event.key == pygame.K_i:
				insertion_sort(z, screen)
			elif event.key == pygame.K_q:
				quick_sort(z, 0, len(z.bar_heights) - 1, screen)
			elif event.key == pygame.K_h:
				heap_sort(z, screen)
			elif event.key == pygame.K_r:
				reset()
	
	pygame.display.update()
