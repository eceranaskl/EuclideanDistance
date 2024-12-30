# EuclideanDistance
Python code for calculating and realizing the minimum Euclidean distance on a 2D space.

The link to the Python code in Google Colab for this project: https://colab.research.google.com/drive/14NW9xN5WnhLxDQ0blNXu2U9aPESsErPi?usp=sharing

The open code source is the following:
#initial Euclidian distance calculation code
x1, y1 = 1, 2
x2, y2 = 3, 4
import math

points = [(x1, y1), (x2, y2)]

def euclideanDistance(x, y):
    distance = math.sqrt((x2-x1)**2 + (y2-y1)**2)
    return distance

for x,y in points:
    print(euclideanDistance(x, y))
    distances = []
    distances.append(euclideanDistance(x, y))
    print(min(distances))

#updated Euclidian distance calculation code 
#it has been updated to have the euclideanDistance function to be reusable
#prints the minimum distance with the corresponding points given
points = [(1, 2), (1, 4), (2, 6), (7, 10)]

def euclideanDistance(point1, point2):
    x1, y1 = point1
    x2, y2 = point2
    return ((x2 - x1)**2 + (y2 - y1)**2)**0.5

distances = []
for i in range(len(points)):
  for j in range(i + 1, len(points)):
    distance = euclideanDistance(points[i], points[j])
    distances.append((distance, points[i], points[j]))

min_distance, point1, point2 = min(distances, key=lambda x: x[0])
print(f"Minimum distance: {min_distance} between points {point1} and {point2}")

