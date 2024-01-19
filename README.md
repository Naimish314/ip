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

2) 2.	Write mysql queries for the PRODUCT table given below:	[7 M]

No	Name	Price	Supplier	Stock
1	Motherboard	7000	Intel	20
2	Keyboard	1000	TVSE	70
3	Mouse	500	Logitech	60
4	Soundcard	600 Samsung	50
5	Speaker	600 Samsung	25
6	Monitor	3000 Philips	22
7	CD-ROM	2800	Creative	32
8	Printer	7900	HP	10

a)	Write mysql command to create the table product and insert records into it.
-ANS- 
-- Create the PRODUCT table
CREATE TABLE PRODUCT (
    No INT PRIMARY KEY,
    Name VARCHAR(255),
    Price INT,
    Supplier VARCHAR(255),
    Stock INT
);
INSERT INTO PRODUCT (No, Name, Price, Supplier, Stock)
VALUES
(1, 'Motherboard', 7000, 'Intel', 20),
(2, 'Keyboard', 1000, 'TVSE', 70),
(3, 'Mouse', 500, 'Logitech', 60),
(4, 'Soundcard', 600, 'Samsung', 50),
(5, 'Speaker', 600, 'Samsung', 25),
(6, 'Monitor', 3000, 'Philips', 22),
(7, 'CD-ROM', 2800, 'Creative', 32),
(8, 'Printer', 7900, 'HP', 10);

b)Display the name and price from the table product in descending order of their stock.
-ANS-
SELECT Name, Price 
FROM PRODUCT 
ORDER BY Stock DESC;

c)Write a command to display the position of ‘a’ in name column.
-ANS-
SELECT POSITION('a' IN Name) AS Position_of_a
FROM PRODUCT;

d)Write a command to extract 3 characters from the 2nd position of supplier column.
-ANS-
SELECT SUBSTRING(Supplier, 2, 3) AS ExtractedChars 
FROM PRODUCT;

e)Display average price of each supplier
-ANS-
SELECT Supplier, AVG(Price) AS AveragePrice F
ROM PRODUCT 
GROUP BY Supplier;

f)Display average price of each supplier whose supplier name is ‘Samsung’.
-ANS-
SELECT Supplier, AVG(Price) AS AveragePrice 
FROM PRODUCT
WHERE Supplier = 'Samsung' 
GROUP BY Supplier;

           SET-2
           



