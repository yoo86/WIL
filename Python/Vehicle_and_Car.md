## 문제 : Vehicle클래스와 Car클래스를 사용해 코드를 작성하시오. (조건에 따라 순서대로 작성)
Create a class called `Vehicle` that has following properties:
- `self.brand`: str: brand of a vehicle
- `self.year`: int: year of a vehicle
- `self.mileage`: int: current mileage of a vehicle
- `self.max_mileage`: int: max mileage of a vehicle
- `self.maintenance_flag`: bool: True if a vehicle needs a maintenance (or repair) and False if a vehicle doesn't need a maintenance

- `repair(self)` method
  - print a message '+++Repair!+++\n'
  - set `maintenance_flag` as False and `mileage` as 0
<pre>
<code>
import random

class Vehicle:
  def __init__(self, brand, year, mileage, max_mileage):
    self.brand = brand
    self.year = year
    self.mileage = mileage
    self.max_mileage = max_mileage
    
  def repair(self):
    print('+++Repair!+++\n')
    maintenance_flag = False
    self.mileage = 0
</code>
</pre>
***
Create a child class called `Car` that inherits all of the properties of the class `Vehicle`. It also has additional properties: 
- `print_status(self)`: that prints out the current mileage status of the car
- `print_info(self)`: that prints out all information of the car including brand, year, mileage, max_mileage.
- `drive(self, drive_miles)` method
  - takes a input of `drive_miles` (integer) 
  - drives a car accordingly
  - prints a message '\*Drive `drive_miles` miles!\*' 
  - and finally, updates a mileage status of the car

  - if mileage stauts is over the max value, we need to set the maintenance flag True
<pre>
<code>
class Car(Vehicle):
  def __init__(self, brand, year, mileage, max_mileage):
    super().__init__(brand, year, mileage, max_mileage)

  def drive(self, drive_miles):
    self.drive_miles = drive_miles

    if self.mileage > self.max_mileage:
      maintenance_flag = True
      super().repair()

    print(f'*Drive {self.drive_miles} miles!*')
    self.mileage += self.drive_miles

  def print_status(self):
    print('>'* self.mileage + '.'*(self.max_mileage-self.mileage))

  def print_info(self):
    print('=========='*3)
    print(f'Brand: {self.brand}, Year: {self.year}')
    print(f'Mileage: {self.mileage}, Max-Mileage: {self.max_mileage}')
    print('=========='*3+'\n')
</code>
</pre>
***
Create a `random_drive_car(car)` function
- that takes an instance `car` of `Car` class as input argument

- determines a `drive_miles` (the distance to drive) as a random integer between 1 and 30
- drives the `car` for `drive_miles` miles
- prints out the status by calling `print_status()` method of a instance `car`

- note that we need to check whether the car needs a maintanence (= repair) or not, and if necessary, we can call `repair()` function
<pre>
<code>
def random_drive_car(car):
  car_miles = random.randint(1, 30)
  car.drive(car_miles)
  car.print_status()
</code>
</pre>
***
### result
<pre>
<code>
# test your code:
carA = Car("AAA", 2010, 13, 100)
carA.print_info()

for i in range(10):
  random_drive_car(carA)

>>
==============================
Brand: AAA, Year: 2010
Mileage: 13, Max-Mileage: 100
==============================

*Drive 14 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>.........................................................................
*Drive 20 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.....................................................
*Drive 18 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>...................................
*Drive 13 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>......................
*Drive 5 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.................
*Drive 22 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
+++Repair!+++

*Drive 15 miles!*
>>>>>>>>>>>>>>>.....................................................................................
*Drive 14 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.......................................................................
*Drive 6 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.................................................................
*Drive 16 miles!*
>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>.................................................
</code>
</pre>
