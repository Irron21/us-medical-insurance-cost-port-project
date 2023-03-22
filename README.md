# us-medical-insurance-cost-port-project

## A functional project made to investigate findings in the given dataset of the US Medical Insurance Cost.

This is a [course portfolio starter project](https://discuss.codecademy.com/c/project/portfolio-project-python-project/1908) that was built in [jupyter notebook](https://jupyter.org/) document using visual studio code as the code editor. Every function in this project are developed to perform different calculation to show result of different ideas for analyzation of the [given dataset](https://raw.githubusercontent.com/Irron21/us-medical-insurance-cost-data-analysis/main/us-medical-insurance-cost-project-files/insurance.csv).

### The procedures that I have done to construct this project:
1. Import [csv](https://docs.python.org/3/library/csv.html) library to help ;
2. Extract the content of the [insurance.csv](https://github.com/Irron21/us-medical-insurance-cost-data-analysis/blob/main/us-medical-insurance-cost-project-files/insurance.csv) file
3. Iterate through every row of the dataset then assign it as a value of each unique key ID
```python
import csv

with open('insurance.csv') as insurance_csv:
    insurance_reader = csv.DictReader(insurance_csv)
    rowcount = 0
    dictionary_data = {}
    for row in insurance_reader:
        rowcount += 1
        dictionary_data[rowcount] = row
```
4. Iterate through every value of each key to pass it as a parameter to each function
5. Construct different functions to make calculations within the scope of the analysis idea, thus, giving us its findings

## Implementations and Results
Q: Find out the average age of the patients in the dataset. <br>
Q: Find out the average bmi of the patients in the dataset.
```python
def get_average(var):
    total = 0
    for values in dictionary_data.values():
        float_conversion = float(values[var])
        total += float_conversion
    average = total / len(dictionary_data)
    return average
    
age_average = int(get_average("age"))
print(f"The average age in the dataset is: {age_average}")
bmi_average = get_average("bmi")
print(f"The average bmi in the dataset is: {round(bmi_average, 2)}")
```

A: The average age in the dataset is: 39 <br>
A: The average bmi in the dataset is: 30.66

---

Q: Count the frequency of each region that appeared in the dataset. <br>
Q: Analyze where a majority of the individuals are from.
```python
region_count = {}
def region_frq(var):
    for values in dictionary_data.values():
        region = values[var]
        if region in region_count:
            region_count[region] += 1
        else:
             region_count[region] = 1
    return region_count

print(region_frq("region"))
max_frq_region_key = max(region_count, key=region_count.get)
print(f"The majority of the individuals are from the {max_frq_region_key} with the count of {max(region_count.values())}")
```
A: southwest: 325 | southeast: 364 | northwest: 325 | northeast: 324 <br>
A: The majority of the individuals are from the southeast with the count of 364.

---

Q: The average charge for smokers and non-smokers. <br>
Q: The difference of the average charge between smokers and non-smokers.
```python
# a function to sum the total charge between 2 smoker categories
total_cost_smoker = {"yes": 0, "no": 0}
def smoker_cost_difference(var1, var2):
    for values in dictionary_data.values():
        smoker = values[var1]
        cost = values[var2]
        total_cost_smoker[smoker] += float(cost)

    return total_cost_smoker

smoker_cost_difference("smoker", "charges")

# calculate the average of "yes"
total_cost_yes = total_cost_smoker["yes"]
num_records_yes = sum(1 for values in dictionary_data.values() if values["smoker"] == "yes")
average_cost_yes = total_cost_yes / num_records_yes
print(f"The average cost for smokers is: ${round(average_cost_yes, 2)}")

# calculate the average of "no"
total_cost_no = total_cost_smoker["no"]
num_records_no = sum(1 for values in dictionary_data.values() if values["smoker"] == "no")
average_cost_no = total_cost_no / num_records_no
print(f"The average cost for non-smokers is: ${round(average_cost_no, 2)}" )

# differentiate the total charge between the 2 smoker categories
charge_difference = average_cost_yes - average_cost_no
print(f"The charge difference between smokers and non-smokers is: ${round(charge_difference, 2)}")
```
A: The average cost for smokers is: $32050.23 | The average cost for non-smokers is: $8434.27 <br>
A: The charge difference between smokers and non-smokers is: $23615.96

---

Q: Figure out what the average age is for someone who has at least one child in this dataset.
```python
def avg_age_w_child(var1, var2):
    total_age = 0
    length = 0
    for values in dictionary_data.values():
        age = int(values[var1])
        children = int(values[var2])
        if children >= 1:
            total_age += age
            length += 1
        else:
            total_age += 0
    avg_age = total_age / length
    return total_age, int(avg_age)

total_age, avg_age = avg_age_w_child("age", "children")
print(f"{avg_age} is the average age for individuals that has atleast 1 children")
```
A: 39 is the average age for individuals that has at least 1 children

## How to install the project
1. Install [Visual Studio Code](https://code.visualstudio.com/) or you can watch this [tutorial video](https://www.youtube.com/watch?v=JPZsB_6yHVo)
2. Download the project file by copying its [url](https://github.com/Irron21/us-medical-insurance-cost-data-analysis/tree/main/python-portfolio-project-starter-files) and navigate into https://download-directory.github.io/ and paste the url of the project directory to the input box then hit enter. <br><br>
![image](https://user-images.githubusercontent.com/106497944/226794192-f87e4e3d-9f03-401c-9ac3-28afbe8e9a84.png)
3. Once finished downloading, extract the zip file.
4. Setup your Visual Studio Code by referring to this [article](https://code.visualstudio.com/docs/datascience/jupyter-notebooks#_setting-up-your-environment)
5. Once settled, you can now open the project folder in Visual Studio Code!

