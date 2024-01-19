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
           

1) (a) Write a program to create a DataFrame Quarterly Sales where each row contains the Quarterly Sales of TV, Fridge and AC [4 M]
   
	TV	FRIDGE	AC
QTR1	200000	300000	240000
QTR2	230000	200000	153000
QTR3	210000	290000	245000
QTR4	240000	210000	170000
-ANS-
import pandas as pd
data = {'TV': [200000, 230000, 210000, 240000],
        'FRIDGE': [300000, 200000, 290000, 2100000],
        'AC': [240000, 153000, 245000, 170000]}
index = ['QTR1', 'QTR2', 'QTR3', 'QTR4']
df = pd.DataFrame(data, index=index)
print(df)

b) Given datasets population of India and Pakistan in the given years. Show the population of India and Pakistan using line chart with title and labels of both axis.
[4 M]
YEAR	1960	1970	1980	1990	2000	2010
Population of Pakistan 44.91	58.09	78.07	107.7	138.5	170.6
Population of India	449.48	553.57	696.783	870.133	1000.4	1309.1
-ANS-
import matplotlib.pyplot as plt
years = [1960, 1970, 1980, 1990, 2000, 2010]
population_pakistan = [44.91, 58.09, 78.07, 107.7, 138.5, 170.6]
population_india = [449.48, 553.57, 696.783, 870.133, 1000.4, 1309.1]
plt.plot(years, population_pakistan, label='Population of Pakistan')
plt.plot(years, population_india, label='Population of India')
plt.title('Population of India and Pakistan (1960-2010)')
plt.xlabel('Year')
plt.ylabel('Population (in million)')
plt.legend()
plt.show()

2. Write Mysql queries for the HOSPITAL table given below:	[7 M]

PNo	Name	Age	Department	Dateofadm	Charges	Gender
1	Arprit	62	Surgery	2008-01-12	300	M
2	Zarina	22	ENT	2007-12-12	250	F
3	Kareem	32	Orthopaedic	2008-02-19	200	M
4	Arun	12	Surgery	2008-01-11	300	M
5	Zubin	30	ENT	2008-01-12	250	M
6	Ketaki	16	ENT	2008-02-24	250	M
7	Ankita	29	Cardiology	2008-02-20	800	F
8	Zareen	45	Gynaecology	2008-02-22	300	F
9	Kush	19	Cardiology	2008-01-13	800	M
10	Shilpa	23	Nuclear Medicine	2008-01-20	400	F

a)Write mysql command to create hospital table and insert records into it.
-ANS-
-- Create the HOSPITAL table
CREATE TABLE HOSPITAL (
    PNo INT PRIMARY KEY,
    Name VARCHAR(255),
    Age INT,
    Department VARCHAR(255),
    Dateofadm DATE,
    Charges INT,
    Gender CHAR(1)
);

INSERT INTO HOSPITAL (PNo, Name, Age, Department, Dateofadm, Charges, Gender)
VALUES
(1, 'Arprit', 62, 'Surgery', '2008-01-12', 300, 'M'),
(2, 'Zarina', 22, 'ENT', '2007-12-12', 250, 'F'),
(3, 'Kareem', 32, 'Orthopaedic', '2008-02-19', 200, 'M'),
(4, 'Arun', 12, 'Surgery', '2008-01-11', 300, 'M'),
(5, 'Zubin', 30, 'ENT', '2008-01-12', 250, 'M'),
(6, 'Ketaki', 16, 'ENT', '2008-02-24', 250, 'M'),
(7, 'Ankita', 29, 'Cardiology', '2008-02-20', 800, 'F'),
(8, 'Zareen', 45, 'Gynaecology', '2008-02-22', 300, 'F'),
(9, 'Kush', 19, 'Cardiology', '2008-01-13', 800, 'M'),
(10, 'Shilpa', 23, 'Nuclear Medicine', '2008-01-20', 400, 'F');

b) To list names of all patients with their date of admission in ascending order
-ANS-
SELECT Name, Dateofadm 
FROM HOSPITAL 
ORDER BY Dateofadm ASC;

c) Display the department wise total charges whose maximum charges more than equal to 300
-ANS- 
SELECT Department, SUM(Charges) AS TotalCharges
FROM HOSPITAL
GROUP BY Department
HAVING MAX(Charges) >= 300;

d) Display the position of ‘a’ in the name column of hospital table.
-ANS-
SELECT Name, POSITION('a' IN Name) AS PositionOfA
FROM HOSPITAL;

e) Write a command to extract 3 characters from 1st position of Department column.
-ANS-
SELECT SUBSTRING(Department, 1, 3) AS ExtractedChars 
FROM HOSPITAL;

f) Display gender wise total charges
SELECT Gender, SUM(Charges) AS TotalCharges 
FROM HOSPITAL 
GROUP BY Gender;

                 SET-3
1.	(a) In an online contest, two 2-player teams point in 4 rounds are stored in two DataFrames as shown below:	[4 M]
Team 1’s points(df1)	Team 2’s points(df2)

	P1	P2		P1	P2
1	700	490	1	1100	1400
2	975	460	2	1275	1260
3	970	570	3	1270	1500
4	900	590	4	1400	1190

Write a program to calculate total points earned by both the teams in each round.
-ANS-
import pandas as pd
df1 = pd.DataFrame({'P1': [700, 975, 970, 900], 'Ps': [490, 460, 570, 590]})
df2 = pd.DataFrame({'P1': [1100, 1275, 1270, 1400], 'P2': [1400, 1260, 1500, 1190]})
total_points = df1 + df2
print(total_points)

(b) Draw the Bar graph based on the production of wheat in different years. [4 M]
Year	2000	2002	2004	2006	2008	2010	2012	2014	2016	2018
Production	4	6	7	15	24	2	19	5	16	4
-ANS-
import matplotlib.pyplot as plt
years = [2000, 2002, 2004, 2006, 2008, 2010, 2012, 2014, 2016, 2018]
production = [4, 6, 7, 15, 24, 2, 19, 5, 16, 4]
plt.bar(years, production, color='skyblue')
plt.xlabel('Year')
plt.ylabel('Production (in millions)')
plt.title('Wheat Production in Different Years')
plt.xticks(years)
plt.tight_layout()
plt.show()

2. Write SQL commands for SPORTS table given below	[7 M]
STUDENTNO CLASS	NAME GAME1 GRADE1	GAME2	GRADE2
10 7 SAMEER CRICKET B SWIMMING	A
11 8 SUJIT TENNIS A SKATING C
12 7 KAMAL SWIMMING B FOOTBALL B
13 7 VEENA TENNIS C TENNIS A
14 9 ARCHANA BASKETBALL A CRICKET	A
15 10 ARPIT CRICKET A ATHLETICS	C
a)	Write mysql command to create sports table and enter records into it.
-ANS-
CREATE TABLE SPORTS (
    STUDENTNO INT,
    CLASS INT,
    NAME VARCHAR(50),
    GAME1 VARCHAR(50),
    GRADE1 CHAR,
    GAME2 VARCHAR(50),
    GRADE2 CHAR
);

INSERT INTO SPORTS VALUES
(10, 7, 'SAMEER', 'CRICKET', 'B', 'SWIMMING', 'A'),
(11, 8, 'SUJIT', 'TENNIS', 'A', 'SKATING', 'C'),
(12, 7, 'KAMAL', 'SWIMMING', 'B', 'FOOTBALL', 'B'),
(13, 7, 'VEENA', 'TENNIS', 'C', 'TENNIS', 'A'),
(14, 9, 'ARCHANA', 'BASKETBALL', 'A', 'CRICKET', 'A'),
(15, 10, 'ARPIT', 'CRICKET', 'A', 'ATHLETICS', 'C');


b) Display the names of the students who have grade ‘C’ in either Game1 or Game2 or both
-ANS-
SELECT NAME 
FROM SPORTS 
WHERE GRADE1 = 'C' OR GRADE2 = 'C';

c) Write a command to concatenate name and game1 columns of sports table
-ANS-
SELECT CONCAT(NAME, ' - ', GAME1) AS Concatenated_Column 
FROM SPORTS;

d) Display the position of ‘e’ in the name column of sports.
-ANS-
SELECT POSITION('e' IN NAME) AS Position_Of_E 
FROM SPORTS;


e) Display maximum studentno class wise.
-ANS-
SELECT CLASS, MAX(STUDENTNO) AS Max_Student_No 
FROM SPORTS 
GROUP BY CLASS;

f)	Display maximum studentno class wise whose studentno is more than 7.
-ANS-
SELECT CLASS, MAX(STUDENTNO) AS Max_StudentNo 
FROM SPORTS 
WHERE STUDENTNO > 7 
GROUP BY CLASS;
