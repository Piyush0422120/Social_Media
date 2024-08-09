# Social_Media
Objective: Analysis of a social media platform

Total number of Queries: 27  <br><br>
![image](https://github.com/user-attachments/assets/3a64658a-ae1e-4189-bf4b-cbded223d4da)

---
## SNAPSHOTS  


#1 Biggest Daily Gain <BR>

```
-- Query 1
-- Biggest daily gain (24 hr) (Top 10)

SELECT _Date,
       change_in_percent
FROM nifty_analysis
ORDER BY change_in_percent DESC
LIMIT 10;
```
![image](https://github.com/user-attachments/assets/be3a8523-d62a-4290-a5be-625e9eebc6b4)

<BR>

#2 Selecting yearly gains according to gain% <BR>

```
-- Query 5
-- Selecting yearly gains according to gain% (CAUTION: 2014 and 2024 are not full calendar years)

SELECT _Year,
       ROUND(percent_gain_or_loss,3) AS percent_gain_or_loss
FROM yearly_gains
ORDER BY percent_gain_or_loss DESC;

```
![image](https://github.com/user-attachments/assets/cbc42440-184e-4542-9434-973ed09ebd4d)

<BR>

#3 M-o-M gains <BR>

```
-- Query 9
-- M-o-M gains

SELECT  Month_number,
        Month_name,
        Years,
        ROUND(Percentage_gain,3) AS Monthly_gains
FROM Monthly_gains
ORDER BY  Years;

```
![image](https://github.com/user-attachments/assets/e5963c83-1570-41e7-979a-0f8923a1c880)

<BR>

#4 Selecting months on basis of avg_monthly gains <BR>

```
-- Query 10
-- Selecting months on basis of avg_monthly gains

SELECT  Month_number,
        Month_name,
        ROUND(AVG(Percentage_gain),3) AS avg_Monthly_gains
FROM Monthly_gains
GROUP BY Month_number, Month_name
ORDER BY avg_Monthly_gains DESC;

```
![image](https://github.com/user-attachments/assets/dc007076-5cb6-4c65-9662-a2ea99b5da10)

<BR>

#5 Average P/E, P/B, Div_yield (10 years)  <BR>

```
-- Query 12
-- Average P/E, P/B, Div_yield (10 years)

SELECT  ROUND(AVG(pe),3) AS PE_ratio_avg,
        ROUND(AVG(pb),3) AS PB_ratio_avg,
        ROUND(AVG(Div_yield_percent),3) AS Div_yield_avg
FROM nifty_analysis;

```
![image](https://github.com/user-attachments/assets/4c14a11b-e576-47d9-b1c8-b06b3f47afb6)

<BR>

#6 Average P/E, P/B, Div_yield for every year from 2014-2024  <BR>

```
-- Query 14
-- Average P/E, P/B, Div_yield for every year from 2014-2024

SELECT  YEAR(_Date) as Years,
        ROUND(AVG(pe),3) AS PE_ratio_avg,
        ROUND(AVG(pb),3) AS PB_ratio_avg,
        ROUND(AVG(Div_yield_percent),3) AS Div_yield_avg
FROM nifty_analysis
GROUP BY YEAR(_date);

```
![image](https://github.com/user-attachments/assets/9b6d176c-a32b-4696-a675-ab80d976d91e)

<BR>
