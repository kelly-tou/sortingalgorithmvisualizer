import pygame
from bar import bar_array

def is_sorted(arr):
	for i in range(len(arr)-1):
		if arr[i]>arr[i+1]:
			return False
	return True

def bubble_sort(bars, screen):
	sorts = False
	while not sorts:
		for i in range(len(bars.bar_heights)-1):
			if bars.bar_heights[i]>bars.bar_heights[i+1]:
				temp = bars.bar_heights[i]
				bars.bar_heights[i] = bars.bar_heights[i+1]
				bars.bar_heights[i+1] = temp
			screen.fill((2,6,33))
			bars.draw(screen, i, i+1)
			pygame.display.update()
		if is_sorted(bars.bar_heights):
			sorts = True

def insertion_sort(bars, screen):
	sorts = False
	while not sorts:
		for i in range(1, len(bars.bar_heights)):
			val = bars.bar_heights[i]
			j = i - 1
			while j >= 0:
				if val < bars.bar_heights[j]:
					bars.bar_heights[j+1] = bars.bar_heights[j]
					bars.bar_heights[j] = val
					screen.fill((2,6,33))
					bars.draw(screen, j, j+1)
					pygame.display.update()
					j = j - 1
				else:
					break
		if is_sorted(bars.bar_heights):
			sorts = True

def quick_sort(bars, left, right, screen):
	if left<right:
		divide_pos = divide(bars, left, right, screen)
		quick_sort(bars, left, divide_pos - 1, screen)
		quick_sort(bars, divide_pos + 1, right, screen)

def divide(bars, left, right, screen):
	i = left
	j = right - 1
	pivot = bars.bar_heights[right]
	while i < j:
		while i < right and bars.bar_heights[i] < pivot:
			screen.fill((2,6,33))
			bars.draw(screen, i, right)
			pygame.display.update()
			i+=1
		while j > left and bars.bar_heights[j] >= pivot:
			screen.fill((2,6,33))
			bars.draw(screen, left, j)
			pygame.display.update()
			j -= 1
		if i < j:
			bars.bar_heights[i], bars.bar_heights[j] = bars.bar_heights[j], bars.bar_heights[i]
			screen.fill((2,6,33))
			bars.draw(screen, i, j)
			pygame.display.update()
	if bars.bar_heights[i] > pivot:
		bars.bar_heights[i], bars.bar_heights[right] = bars.bar_heights[right], bars.bar_heights[i]
		screen.fill((2,6,33))
		bars.draw(screen, i, right)
		pygame.display.update()
	return i

def sift(bars, i, upper, screen):
	while True:
		l, r = i*2+1, i*2+2
		if max(l, r) < upper:
			if bars.bar_heights[i] >= max(bars.bar_heights[l], bars.bar_heights[r]):
				break
			elif bars.bar_heights[l] > bars.bar_heights[r]:
				bars.bar_heights[i], bars.bar_heights[l] = bars.bar_heights[l], bars.bar_heights[i]
				screen.fill((2,6,33))
				bars.draw(screen, i, l)
				pygame.display.update()
				i = l
			else:
				bars.bar_heights[i], bars.bar_heights[r] = bars.bar_heights[r], bars.bar_heights[i]
				screen.fill((2,6,33))
				bars.draw(screen, i, r)
				pygame.display.update()
				i = r
		elif l < upper:
			if bars.bar_heights[l] > bars.bar_heights[i]:
				bars.bar_heights[i], bars.bar_heights[l] = bars.bar_heights[l], bars.bar_heights[i]
				screen.fill((2,6,33))
				bars.draw(screen, i, l)
				pygame.display.update()
				i = l
			else:
				break
		elif r<upper:
			if bars.bar_heights[r] > bars.bar_heights[i]:
				bars.bar_heights[i], bars.bar_heights[r] = bars.bar_heights[r], bars.bar_heights[i]
				screen.fill((2,6,33))
				bars.draw(screen, i, r)
				pygame.display.update()
				i = r
			else:
				break
		else:
			break

def heap_sort(bars, screen):
	for i in range((len(bars.bar_heights)-2)//2, -1, -1):
		sift(bars, i, len(bars.bar_heights), screen)
	for end in range(len(bars.bar_heights)-1, 0, -1):
		bars.bar_heights[0], bars.bar_heights[end] = bars.bar_heights[end], bars.bar_heights[0]
		sift(bars, 0, end, screen)
