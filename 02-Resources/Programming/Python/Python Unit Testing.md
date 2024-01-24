---
title: Python Unit Testing
Created: 2023-10-19 20:18
tags:
  - python
aliases:
---
# Python Unit Testing
- Testing a single *unit* of a program
- Testing a on function, loop, or a variable.

```Python
def time_ten(number):
	return number * 10

def test_multiply_ten_by_zero():
	assert times_ten(0) == 0, 'Expected times_ten(0) to return 0'

def test_multiply_ten_by_negative_number():
	assert times_ten(-10) == -100 'Expected times_ten(-10) to return -100'
```
>[!note] This is a very basic way to perform tests

## unittest Framework
- A built-in framework of unit testing.

```Python
import unittest
```

>[!tip] The `unittest` module requires that test functions begin with the word *test*

- Provides a *test runner* which collects and executes tests and then provides the results to the user.
- Provides many tools for test grouping, setup, teardwon, skipping and many other functions.
- The framework relies on built-in assert methods.
	- **assertEqual**: `self.assertEqual(val1, val2)` Takes two values as arguements and checks that they are equal. If they are not, the test fails
	- **assertin**: `self.assertIn(val, container)` Takes two arguments and checks if the first argument is found in the second argument which should be a container. If not found the test returns false.
	- **assertTrue**: `self.assertTrue(val)` takes a single argument and checks that argument evaluates to True. Else the test fails.

```Python
class TestTimesTen(unittest.TestCase):
	def test_multiply_ten_by_zero(self):
		self.assertEqual(times_ten(0), 0, 'Expected times_ten(0) to return 0')
	def test_multiply_ten_by_one_million(self):
		self.assertEqual(times_ten(1000000), 1000000, 'Expected time_ten(1000000) to return 1000000')
	def test_multiply_ten_by_negative_numver(self):
		self.assertEqual(times(-10), -100, 'Expected times_ten(-10) to return -100')
```

- To run the unit test use `unittest.main()`

## Quantitative Methods
- Great for testing conditions related to numbers. There are a handful of methods for this testings.
	- **assertLess**: `self.assertLess(val1, val2)` Takes two arguments and checks that the first argument is less than the second one. If it is not, the test will fail.
	- **assertAlmostEqual**: `self.assertAlmostEqual(val1, val2)` Takes two arguments and checks that their difference, when rounded to 7 decimal places, is 0. If the values are not close enough, the test will fail. 

## Exception and Warning Methods
>[!tip] Do not call the function with parenthesis. Simply use the function name only

- **assertRaises**: Takes an exception type as its first argument, a function reference as its second, and an arbitrary number of arguments as the rest.
	- Calls the function and checks if an exception is raised.
	- The test passes if an exception is raised
		- Will throw an error if another type of exception is raised.
	- The test fails if no exception is raised.
```Python
self.assertRaises(specificException, function, functionArguments)
```

- **assertWarns**: Takes a warning type as its first argument, a function references as it second, and an arbitrary number of arguments for the rest.
	- Calls the function and checks that the warning occurs. 
	- Test passes if a warning is triggered
	- Fails if no warning is trigged
```Python
self.assertWarns(specificWarningException, function, functionArguments)
```

## Parametering Tests
- Python provides a toolset of tests with only minor differences.
- We can use the **subTest** context manager. [Documentation](https://docs.python.org/3/library/unittest.html#distinguishing-test-iterations-using-subtests)
- Each iteration of the loop is treated as an individual test.
	- A failure is returned as a seperate test case.
	  
```Python
import unittest

def times_ten(number):
	return number * 100

class TestTimesTen(unittest.TestCase):
	def test_times_ten(self):
		for num [0,1000000, -10]:
			with self.subTest(num):
				expected_result = num * 10
				message = 'Expected times_ten(' + str(num) + ') to return ' + str(expected_result)
				self.assertEqual(times_ten(num), expected_result, message)

```

>[!warning] Don't forget to reset the state of the object in each loop
## Test Fixtures
- A mechanism for ensuring proper test setup and teardown.
	- **setup**: putting tests into a known state
	- **teardown**: restoring the state prior to test running.
- Will automatically identify setup and teardown methods based on their name.


```Python
def power_cycle_device():
	print("Power Cycling bluetooth device...")

class BluetooDeviceTests(unittest.TestCase):
	def setUp(self):
		power_cycle_device()
	def test_feature_a(self):
		print('Testing Feature A')
	def test_feature_b(Self):
		print('Testing Feature B')
	def tearDown(self):
		power_cycle_device()
```
>[!note] setUp runs before each test case in the class. tearDown gets called after each test case.

```Python
def power_cycle_device():
	print("Power Cycling bluetooth device...")

class BluetooDeviceTests(unittest.TestCase):
	@classmethod
	def setUp(cls):
		power_cycle_device()
	def test_feature_a(self):
		print('Testing Feature A')
	def test_feature_b(Self):
		print('Testing Feature B')
	@classmethod	
	def tearDown(cls):
		power_cycle_device()
```
>[!note] This will setup the tests, run all the test, then teardown.


## Skipping Tests
- For situations when test should only run in a particular context. Like certain operating systems.
- The `unittest` framework provides two different ways to skip tests.
	- `@unittest` skip decorator
	- `skipTest()` method
>[!tip] When the conditions for skipping a test are too complicated to pass into a skip decorateor, the `skipTest` method is the alternative

```Python
import sys

class LinuxTest(unittest.TestCase):
	@unittest.skipunless(sys.platform.startswith("linux"), "This test only runs on linux")
	def test_linux_feature(self):
		print("This test should only run on linux")
	@unittest.skipif(not sys.platform.startswith("linux"), "This test only runs on Linux")
	def test_other_linux_features(self):
		print("This test should only run on linux")
```

- **skipUnless**: skips the test if the condition evaluates to False.
- **skipIf**: option skips the test if the condition evaluatest to True.

```Python
import sys

class LinuxTests(unittest.TestCase):
	def test_linux(self):
		if not sys.platform.startswith("linux"):
			self.skipTest("Test only runs on Linux")
```

## Expected Failures
- Expected failures are counted as a *pass* test result
- If a test passes when expected to fail, it is marked as a *failed* test result
- Use the `@unittest.expectedFailure` decorator

```Python
class FeatureTests(unittest.Testcase):

	@unittest.expectedFailure
	def test_broken_feature(self):
		raise Exception("This test is going to fail")
```