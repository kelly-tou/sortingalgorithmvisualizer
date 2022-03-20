import pygame
import random

class bar_array:
	def __init__(self, num_bars):
		self.num_bars = num_bars
		self.bar_width = (480-5*num_bars)/num_bars
		self.bar_heights = []
		for i in range(num_bars):
			height = random.randint(10,225)
			self.bar_heights.append(height)
		self.sorts = False
		# spacing of 5 units between each bar, spacing of 10 units on left and right ends

	def draw(self, screen, a = None, b = None):
		for i in range(self.num_bars):
			if i == a:
				pygame.draw.rect(screen, (244,248,117), (10+(i*(self.bar_width + 5)), 300-self.bar_heights[i], self.bar_width, self.bar_heights[i]))
			elif i == b:
				pygame.draw.rect(screen, (162,43,197), (10+(i*(self.bar_width + 5)), 300-self.bar_heights[i], self.bar_width, self.bar_heights[i]))
			else:
				pygame.draw.rect(screen, (251, 0, 123), (10+(i*(self.bar_width + 5)), 300-self.bar_heights[i], self.bar_width, self.bar_heights[i]))
