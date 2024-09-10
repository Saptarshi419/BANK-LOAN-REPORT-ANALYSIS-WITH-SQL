Overview:

"In order to monitor and assess our bank's lending activities and performance, we need to create a comprehensive Bank Loan Report. This report aims to provide insights into key loan-related metrics and their changes over time. The report will help us make data-driven decisions, track our loan portfolio's health, and identify trends that can inform our lending strategies.

Key Performance Indicators (KPIs) Requirements:

1.	Total Loan Applications: We need to calculate the total number of loan applications received during a specified period. Additionally, it is essential to monitor the Month-to-Date (MTD) Loan Applications and track changes Month-over-Month (MoM).

2.	Total Funded Amount: Understanding the total amount of funds disbursed as loans is crucial. We also want to keep an eye on the MTD Total Funded Amount and analyse the Month-over-Month (MoM) changes in this metric.

3.	Total Amount Received: Tracking the total amount received from borrowers is essential for assessing the bank's cash flow and loan repayment. We should analyse the Month-to-Date (MTD) Total Amount Received and observe the Month-over-Month (MoM) changes.

4.	Average Interest Rate: Calculating the average interest rate across all loans, MTD, and monitoring the Month-over-Month (MoM) variations in interest rates will provide insights into our lending portfolio's overall cost.

5.	Average Debt-to-Income Ratio (DTI): Evaluating the average DTI for our borrowers helps us gauge their financial health. We need to compute the average DTI for all loans, MTD, and track Month-over-Month (MoM) fluctuations.





Good Loan v Bad Loan KPI’s

In order to evaluate the performance of our lending activities and assess the quality of our loan portfolio, we need to create a comprehensive report that distinguishes between 'Good Loans' and 'Bad Loans' based on specific loan status criteria

Good Loan KPIs:

1.	Good Loan Application Percentage: We need to calculate the percentage of loan applications classified as 'Good Loans.' This category includes loans with a loan status of 'Fully Paid' and 'Current.'

2.	Good Loan Applications: Identifying the total number of loan applications falling under the 'Good Loan' category, which consists of loans with a loan status of 'Fully Paid' and 'Current.'

3.	Good Loan Funded Amount: Determining the total amount of funds disbursed as 'Good Loans.' This includes the principal amounts of loans with a loan status of 'Fully Paid' and 'Current.'

4.	Good Loan Total Received Amount: Tracking the total amount received from borrowers for 'Good Loans,' which encompasses all payments made on loans with a loan status of 'Fully Paid' and 'Current.'


Bad Loan KPIs:

1.	Bad Loan Application Percentage: Calculating the percentage of loan applications categorized as 'Bad Loans.' This category specifically includes loans with a loan status of 'Charged Off.'

2.	Bad Loan Applications: Identifying the total number of loan applications categorized as 'Bad Loans,' which consists of loans with a loan status of 'Charged Off.'

3.	Bad Loan Funded Amount: Determining the total amount of funds disbursed as 'Bad Loans.' This comprises the principal amounts of loans with a loan status of 'Charged Off.'

4.	Bad Loan Total Received Amount: Tracking the total amount received from borrowers for 'Bad Loans,' which includes all payments made on loans with a loan status of 'Charged Off.'


Loan Status Grid View

In order to gain a comprehensive overview of our lending operations and monitor the performance of loans, we aim to create a grid view report categorized by 'Loan Status.' This report will serve as a valuable tool for analyzing and understanding the key indicators associated with different loan statuses. By providing insights into metrics such as 'Total Loan Applications,' 'Total Funded Amount,' 'Total Amount Received,' 'Month-to-Date (MTD) Funded Amount,' 'MTD Amount Received,' 'Average Interest Rate,' and 'Average Debt-to-Income Ratio (DTI),' this grid view will empower us to make data-driven decisions and assess the health of our loan portfolio.


Key Learning From This Project:

i.	Creating Data Base in MS SQL Server

ii.	SQL Join Functions

iii.	Data Cleaning

iv.	SUM, COUNT, COUNTD, AVG Functions in SQL


Project Stages:

I have done this project in MS SQL Server.

First, we have created a Database in the name of Financial Loan

Next, we have imported the .csv flat file to the Database and started Firing Query. 


Quires Used in This Project:


KPI’s:
1.	Total Loan Applications (KPI 1)
select COUNT(id) as Total_Loan_Applications from financial_loan

![image](https://github.com/user-attachments/assets/6532334b-9544-4743-adfa-3e9edc3b191d)

 

Month to Date Loan Application

select COUNT(id) as Month_to_Date_Total_Loan_Applications from financial_loan
where month(issue_date) = 12 and year(issue_date) = 2021

![image](https://github.com/user-attachments/assets/1a1054de-9e1e-4fd1-b23a-11cdb63fd989)

 
Previous Month to Date Loan Applications

select COUNT(id) as Previous_Month_to_Date_Total_Loan_Applications from financial_loan
where month(issue_date) = 11 and year(issue_date) = 2021

![image](https://github.com/user-attachments/assets/1bdc8c96-355b-4f59-bd6a-37e7292bfcb8)

 
2.	Total Funded Amount (KPI 2)

Select sum(loan_amount) as Total_Funded_Amount from financial_loan

![image](https://github.com/user-attachments/assets/acc8e2d5-1275-4e05-b6d3-3bbfd910a6cf)

 
Month to Date Total Funded Amount

Select sum(loan_amount) as Month_To_Date_Total_Funded_Amount from financial_loan
where month(issue_date) = 12 and year(issue_date) = 2021

![image](https://github.com/user-attachments/assets/13e35891-2d5e-4d29-a2f2-67a2d43df28c)

 





Previous Month to Date Total Funded Amount

Select sum(loan_amount) as Previous_Month_To_Date_Total_Funded_Amount from financial_loan
where month(issue_date) = 11 and year(issue_date) = 2021

![image](https://github.com/user-attachments/assets/3908e551-2356-4f28-abcb-7f917bcfdb2b)

 

3.	Total Amount Collected (KPI 3)

Select sum(total_payment) as Total_Amount_Collected from financial_loan

 ![image](https://github.com/user-attachments/assets/9dfd6196-3af9-40b7-b04e-f9be413ff3d6)


Month to Date Total  Amount Collected

Select sum(total_payment) as Month_to_date_Total_Amount_Collected from financial_loan
where month(issue_date) = 12 and year(issue_date) = 2021

![image](https://github.com/user-attachments/assets/3e0d9ca4-f443-414e-9e53-3be58b172702)

 


Previous Month to Date Total  Amount Collected

Select sum(total_payment) as Previous_Month_to_date_Total_Amount_Collected from financial_loan where month(issue_date) = 11 and year(issue_date) = 2021

![image](https://github.com/user-attachments/assets/753e49bf-6b58-42a0-bb6e-c7982b33490a)
 

4.	Average Interest Rate (KPI 4)

select AVG(int_rate) * 100 as Avg_Interest_Rate from financial_loan

![image](https://github.com/user-attachments/assets/c953033f-bcea-4241-9385-a4ac08133074)
 



Month to Date Avarage Interest Rate

select AVG(int_rate) * 100 as MTD_Avg_Interest_Rate from financial_loan
where month(issue_date) = 12 and year(issue_date) = 2021

 ![image](https://github.com/user-attachments/assets/3860969e-160b-44c0-aee6-2de144976884)


Previous Month to Date Avarage Interest Rate

select AVG(int_rate) * 100 as PMTD_Avg_Interest_Rate from financial_loan where month(issue_date) = 11 and year(issue_date) = 2021

![image](https://github.com/user-attachments/assets/a1a36238-b106-4cad-817a-8f5766a466d8)
 


5.	Avg DIT (KPI 5)

select AVG(dti) * 100 as Avg_DTI from financial_loan

 ![image](https://github.com/user-attachments/assets/d7d2af5a-21f6-4b60-927f-854bd590b3e7)


Month to Date Avg DTI

select AVG(dti) * 100 as MTD_Avg_DTI from financial_loan where MONTH(issue_date) = 12 and YEAR(issue_date) = 2021

![image](https://github.com/user-attachments/assets/fa875b49-d6eb-473a-abb5-698c157cf14d)

 

Previous Month to Date Avg DTI

select AVG(dti) * 100 as PMTD_Avg_DTI from financial_loan
where MONTH(issue_date) = 11 and YEAR(issue_date) = 2021

![image](https://github.com/user-attachments/assets/21b7c1de-6770-44f7-b996-8b0c1a8c05f0)


GOOD LOAN ISSUED


Good Loan Percentage:

select(count(case when loan_status = 'Fully Paid' or loan_status = 'Current' then id end) * 100) / count(id) as Good_Loan_Percentage from financial_loan

![image](https://github.com/user-attachments/assets/7c1d3848-e64e-47ae-bf36-6dea38cb846f)

 
Good Loan Applications

select count(id) as Good_Loan_Applications from financial_loan
where loan_status = 'Fully Paid' or loan_status = 'Current'

![image](https://github.com/user-attachments/assets/3dc865a6-a191-489f-8181-4a971ee38c19)

 
Good Loan Funded Amount

select sum(loan_amount) as Good_Loan_Funded_Amount from financial_loan
where loan_status = 'Fully Paid' or loan_status = 'Current'

![image](https://github.com/user-attachments/assets/7930fab0-11f5-40e9-b8bc-9049e6d98ec9)

 

Good Loan Total Received Amount

select sum(total_payment) as Good_Loan_Received_Amount from financial_loan
where loan_status = 'Fully Paid' or loan_status = 'Current'

![image](https://github.com/user-attachments/assets/0c4da42d-f4a3-4df2-850b-25e1d8fd9f07)

 


BAD LOAN ISSUED

Bad Loan Application Percentage
Select (count(case when loan_status = 'Charged Off' then id end) * 100)/ count(id) as Bad_Loan_Percentage from financial_loan

![image](https://github.com/user-attachments/assets/72f805d7-c33e-457f-a2b7-3e0d70bc2ea6)

 

Bad Loan Applications

select COUNT(id) as Bad_loan_Applications from financial_loan
where loan_status = 'Charged Off'

![image](https://github.com/user-attachments/assets/d685e905-04fb-43c3-b3d7-af2dab48a3c8)

 



Bad Loan Funded Amount

select SUM(loan_amount) as Bad_loan_Funded_Amount from financial_loan
where loan_status = 'Charged Off'

![image](https://github.com/user-attachments/assets/41e72835-bdb8-4e5d-87ee-53474f4cd493)

 

Bad Loan Received Amount

select SUM(total_payment) as Bad_loan_Received_Amount from financial_loan
where loan_status = 'Charged Off'

![image](https://github.com/user-attachments/assets/0ede7c9e-6288-4a38-bf0d-2d6a1ab1de54)

 

LOAN STATUS

Select
      loan_status,
	  COUNT(id) as Total_Loan_Applications,
	  SUM(total_payment) as Total_Amount_Received,
	  SUM(loan_amount) as Total_Funded_Amount,
	  AVG(int_rate * 100) as Interest_Rate,
	  AVG(dti * 100) as DTI
	  from financial_loan
	  group by loan_status

   ![image](https://github.com/user-attachments/assets/b86ba9dd-710b-4b48-bf5d-900d5a6e084f)

 
Current Month

select
      loan_status,
	  SUM(total_payment) as MTD_Total_Loan_Amount_Received,
	  SUM(loan_amount) as MTD_Total_Funded_Amount
	  from financial_loan
	  where MONTH(issue_date) = 12
	  group by loan_status


![image](https://github.com/user-attachments/assets/1310d5d5-996d-4c10-8209-db53001a255c)

   
 
A.	BANK LOAN REPORT | OVERVIEW

MONTH

select
      MONTH(issue_date) as Month_Number,
	  DATENAME(MONTH, issue_date) as Month_Name,
	  COUNT(id) as Total_Loan_Applications,
	  SUM(loan_amount) as Total_Funded_Amount,
	  SUM(total_payment) as Total_Received_Amount
	  from financial_loan
	  group by Month(issue_date),  DATENAME(MONTH, issue_date)
	  order by Month(issue_date)

 ![image](https://github.com/user-attachments/assets/42c32718-d353-4d31-b51e-60536833f5b4)




STATE

select
      address_state,
	  COUNT(id) as Total_Loan_Applications,
	  SUM(loan_amount) as Total_Funded_Amount,
	  SUM(total_payment) as Total_Received_Amount
	  from financial_loan
	  group by address_state
	  order by address_state
  
   ![image](https://github.com/user-attachments/assets/d03bc35d-86bd-4366-aa86-68a182d64422)

 




TERM

select
      term,
	  COUNT(id) as Total_Loan_Applications,
	  SUM(loan_amount) as Total_Funded_Amount,
	  SUM(total_payment) as Total_Received_Amount
	  from financial_loan
	  group by term
	  order by term

   ![image](https://github.com/user-attachments/assets/f37873e6-302f-4276-9720-c1e114a766e6)

 

EMPLOYEE LENGTH

select
      emp_length,
	  COUNT(id) as Total_Loan_Applications,
	  SUM(loan_amount) as Total_Funded_Amount,
	  SUM(total_payment) as Total_Received_Amount
	  from financial_loan
	  group by emp_length
	  order by emp_length
  
   ![image](https://github.com/user-attachments/assets/ded9da88-3061-43e9-a19d-9e6896585c59)

 





PURPOSE

select
      purpose as Purpose,
	  COUNT(id) as Total_Loan_Applications,
	  SUM(loan_amount) as Total_Funded_Amount,
	  SUM(total_payment) as Total_Received_Amount
	  from financial_loan
	  group by purpose
	  order by purpose
  
   ![image](https://github.com/user-attachments/assets/2c64cddd-001a-4b9f-97ac-c6a9803d128e)

 

HOME OWNERSHIP

select
      home_ownership as HOME_OWNERSHIP,
	  COUNT(id) as Total_Loan_Applications,
	  SUM(loan_amount) as Total_Funded_Amount,
	  SUM(total_payment) as Total_Received_Amount
	  from financial_loan
	  group by home_ownership
	  order by home_ownership

   ![image](https://github.com/user-attachments/assets/3f7715e4-4e49-4208-8a9b-735f0d24ff09)

 




 

