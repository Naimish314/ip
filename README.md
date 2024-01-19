       SET-1 
  1.	(a) Consider the Series object S that stores the contribution of each section, as shown below:	[4 M]
A	4300
B	6500
C	3900
D	6100
dtype: int64
Write code to modify the amount of Section ‘A’ as 3400 and for section ‘C’ and ‘D’ as 5000 and print the changed object.
-ANS-
import pandas as pd
S = pd.Series([4300, 6500, 3900, 6100], index=['A', 'B', 'C', 'D'], dtype=int)
S['A'] = 3400
S['C'] = 5000
S['D'] = 5000
print(S)

(b)Given the school result data, analysis the performance of the students in Accountancy & Business Studies using line graph.	[4 M]
Names	Ram	Shyam	Rama Kashish Mayank
Accountancy	87	82	99	85	80
Business Studies	90	79	95	93	85
-ANS-
import matplotlib.pyplot as plt
names = ['Ram', 'Shyam', 'Rama', 'Kashish', 'Mayank']
accountancy_scores = [87, 82, 99, 85, 80]
business_studies_scores = [90, 79, 95, 93, 85]
plt.figure(figsize=(10, 5))
plt.plot(names, accountancy_scores, marker='o', label='Accountancy')
plt.plot(names, business_studies_scores, marker='o', label='Business Studies')
plt.title('Performance in Accountancy & Business Studies')
plt.xlabel('Names')
plt.ylabel('Scores')
plt.legend()
plt.grid(True)
plt.show()

