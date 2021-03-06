
# Usage with example

```
import BMICalculator import BMIRiskCaculator as BRC

# sample input data
InputData = [
        { "Gender": "Female", "HeightCm": 166, "WeightKg": 62},
        {"Gender": "Female", "HeightCm": 150, "WeightK": 70},
        {"Gender": "Female", "HeightCm": 167, "WeightKg": 82}
    ]

# Calulate the bmi for the above records and stores the data
bmi_calc = BRC.BMIRiskCalculator()
bmi_calc.Calculate (*InputData)

# Interface (instance method) to fetch all the records processed so far (yields dict)
for i in bmi_calc.GetProcessedData():
    print(i)

# Interface (instance method) to fetch all the fault records so far (yields dict)
for i in bmi_calc.GetFaultData():
    print(i)

# Interface (instance method) to fetch total count of people in a given category (returns int)
print("People with over weight: ", bmi_calc.GetNumPeopleWithCategory("Overweight"))

# Interface (instance method) to fetch total count of people having given health risk (returns int)
print("People with over weight: ", bmi_calc.GetNumPeopleWithRisk("Enhanced risk"))

```


# Testing

Run the following coammnd from the project directory to run the unit tests
```
python -m unittest -v
```

# CI Intergartion

```
# steps to get the tests coverage report

1. pip install coverage
2. coverage run -m unittest discover
3. coverage <report file type to generate ex. json, xml, etc.>

# steps to generate the package to distribute

1. python setup.py sdist 

```
