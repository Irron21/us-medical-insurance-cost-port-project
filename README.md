# us-medical-insurance-cost-port-project

## A functional project made to investigate findings in the given dataset of the US Medical Insurance Cost.

This is a [course portfolio starter project](https://discuss.codecademy.com/c/project/portfolio-project-python-project/1908) that was built in [jupyter notebook](https://jupyter.org/) document using visual studio code as the code editor. Every function in this project are developed to perform different calculations to showcase result of different ideas for analyzation of the US Medical Insurance Cost dataset. 

## [US Medical Insurance Cost Dataset](https://raw.githubusercontent.com/Irron21/us-medical-insurance-cost-data-analysis/main/us-medical-insurance-cost-project-files/insurance.csv)
The dataset contains each patient's medically relevent information and other information.
* **age** - age of the patient
* **sex** - sex of the patient
* **bmi** - body mass index of the patient
* **children** - number of children of the patient
* **smoker** - categorize whether they smoke or not
* **region** - the locale of the patient
* **charges** - the insurance cost of the patient

With the given dataset, we can bring out several implementations like: 
1. The average age and bmi of the patients
2. Finding out where the majority of the patients are from by counting the frequency of each region
3. The average charge for smokers and non-smokers and the difference between the given average of both smokers and non-smokers
4. The average age for someone who has at least one children

## Procedures
1. Import [csv](https://docs.python.org/3/library/csv.html) library to help ;
2. Extract the content of the [insurance.csv](https://github.com/Irron21/us-medical-insurance-cost-data-analysis/blob/main/us-medical-insurance-cost-project-files/insurance.csv) file
3. Iterate through every row of the dataset then assign it as a value of each unique key ID
4. Iterate through every value of each key to pass it as a parameter to each function
5. Construct different functions to make calculations within the scope of the analysis idea, thus, giving us its findings

## Implementations and Results
**Q:** Find out the average age of the patients in the dataset. <br>
**A:** The average age in the dataset is: <ins>39</ins>

**Q:** Find out the average bmi of the patients in the dataset. <br>
**A:** The average bmi in the dataset is: <ins>30.66</ins>

---

**Q:** Count the frequency of each region that appeared in the dataset. <br>
**A:** southwest: <ins>325</ins> | southeast: <ins>364</ins> | northwest: <ins>325</ins> | northeast: <ins>324</ins>

**Q:** Analyze where a majority of the individuals are from. <br>
**A:** The majority of the individuals are from the <ins>southeast</ins> with the count of <ins>364</ins>.

---

**Q:** The average charge for smokers and non-smokers. <br>
**A:** The average cost for smokers is: <ins>$32050.23</ins> | The average cost for non-smokers is: <ins>$8434.27</ins> 

**Q:** The difference of the average charge between smokers and non-smokers. <br>
**A:** The charge difference between smokers and non-smokers is: <ins>$23615.96</ins>

---

**Q:** Figure out what the average age is for someone who has at least one child in this dataset. <br>
**A:** <ins>39</ins> is the average age for individuals that has at least 1 children

