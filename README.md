**Banking Dashboard**

**Problem Statement --**

Develop a basic understanding of risk analytics in banking and financial
services and understand how data is used to minimise the risk of losing
money while lending to customers.

**Solution --**

With our dashboards which are created using Power BI latest tools helps
the company to make a decision based on the applicant's profile like if
the applicant is likely to repay the loan then approving the loan
otherwise not.

**About Dataset --**

This dataset basically contains information about bank details ,various
client details which consists of multiple tables which are interlinked
with each other through keys like primary key and foreign key.

The various tables are Banking Relationship, Client-Banking, Gender,
Investment Advisor and Period.

**Data Cleaning --**

Creating a new column Engagement Timeframe in client-banking column
which tells about the time line of the clients in banks

![](media/image1.png){width="6.268055555555556in" height="2.35in"}

Creating a new column Engagment Days in Client-Banking table how many
days the client spent from the date of joining in banks

![](media/image2.png){width="5.642155511811024in"
height="3.358624234470691in"}

Creating bins for the Estimated Income \< 100000 as low and \<300000 as
Mid with the column named as Income Band in Clients-Banking table.

![](media/image3.png){width="5.650489938757655in"
height="4.075353237095363in"}

Creating a new column named as Processing Fees for the column Fee
Structure like if fee structure is high then processing fee would be
0.05

![](media/image4.png){width="4.933760936132983in"
height="4.100355424321959in"}

**Calculated Functions --**

**Sum :**

> The power bi sum function will add all the numbers in a column and the
> column contains numbers to sum. It returns a decimal number.
>
> **Syntax :**
>
> Sum= SUM(\<column\>)
>
> Example:
>
> Bank Deposit =
>
> SUM(\'Clients - Banking\'\[Bank Deposits\] )

**DistinctCount :**

> Counts the number of distinct values in a column
>
> Syntax:
>
> DISTINCTCOUNT(\<column\>)
>
> Example :
>
> Total Clients = DISTINCTCOUNT(\'Clients - Banking\'\[Client ID\] )

**Sumx :**

> Returns the sum of an expression evaluated for each row in a table.
>
> Syntax:
>
> SUMX(\<table\>, \<expression\>)
>
> Example :
>
> Total Fees = SUMX(\'Clients - Banking\' , \[Total Loan\] \*
> \'Clients - Banking\'\[Processing Fees\] )

**Switch :**

> Evaluated an expression against a list of values and returns one of
> multiple possible result expressions
>
> Syntax :
>
> SWITCH(\<expression\>, \<value\>, \<result\>\[, \<value\>,
> \<result\>\]...\[, \<else\>\])

**DATEDIFF :**

> Returns the number of interval boundaries between two dates.
>
> Syntax :
>
> DATEDIFF(\<Date1\>, \<Date2\>, \<Interval\>)
>
> Example :
>
> Engagment Days = DATEDIFF(\'Clients - Banking\'\[Joined
> Bank\],TODAY(), DAY )

**KPI'S:**

In which followings KPIS are present :

**Total Clients :**

> Total Clients KPI represents total number of clients in banking.
>
> Total Clients = DISTINCTCOUNT(\'Clients - Banking\'\[Client ID\] )
>
> ![](media/image5.png){width="2.558555336832896in"
> height="1.3917869641294838in"}

**Total Loan :**

> Total Loan gives you information about the bank loan + Business
> lending + credit cards balance of particular investor , gender.
>
> Total Loan = \[Bank Loan\] + \[Business Lending\] + \[Credit Cards
> Balance\]
>
> ![](media/image6.png){width="2.5668886701662292in"
> height="1.3751192038495188in"}

**Bank Loan :**

> Bank Loan gives you information what is the loan amount of loan to be
> repaid by the client to bank.
>
> Bank Loan = SUM(\'Clients - Banking\'\[Bank Loans\] )
>
> ![](media/image7.png){width="2.362632327209099in"
> height="1.2446675415573054in"}

**Business Lending :**

> Business lending gives you information about the loan amount given to
> small business.
>
> Business Lending = SUM(\'Clients - Banking\'\[Business Lending\] )
>
> ![](media/image8.png){width="2.6252274715660544in"
> height="1.4001213910761154in"}

**Total Deposit**

> Total Deposit gives you information about the amount deposited by
> particular investors in bank
>
> Total Deposit = \[Bank Deposit\] + \[Savings Account\] + \[Foreign
> Currency Account\] + \[Checking Accounts\]
>
> ![](media/image9.png){width="2.1197397200349957in"
> height="1.1761132983377078in"}

**Total Fees :**

> Total Fees is nothing but the amount charged by the bank for account
> set-up , maintenance charges etc.
>
> Total Fees = SUMX(\'Clients - Banking\' , \[Total Loan\] \*
> \'Clients - Banking\'\[Processing Fees\] )
>
> ![](media/image10.png){width="2.475214348206474in"
> height="1.4334580052493437in"}

**Bank Deposit :**

> Bank deposit is the money put in the bank.
>
> Bank Deposit =
>
> SUM(\'Clients - Banking\'\[Bank Deposits\] )
>
> ![](media/image11.png){width="2.441877734033246in"
> height="1.4001213910761154in"}

**Checking Account Amount :**

> Checking account amount is nothing but which offers easy access to
> your money for daily transactional needs.
>
> Checking Accounts =
>
> SUM(\'Clients - Banking\'\[Checking Accounts\] )
>
> ![](media/image12.png){width="2.1376279527559054in"
> height="1.1945570866141733in"}

**Total CC Amount :**

> Total CC Amount is a short-term source of financing for a company by a
> bank.
>
> Total CC Amount = SUM(\'Clients - Banking\'\[Amount of Credit Cards\]
> )
>
> ![](media/image13.png){width="2.475214348206474in"
> height="1.3584514435695538in"}

**Saving Account Amount :**

> A savings account is an interest-bearing deposit account held at a
> bank.
>
> Savings Account = SUM(\'Clients - Banking\'\[Saving Accounts\] )
>
> ![](media/image14.png){width="2.550220909886264in"
> height="1.3751192038495188in"}

**Foreign Currency Amount :**

> Foreign Currency Account means an account held in a currency that is
> not the currency of India or Bhutan or Nepal.
>
> Foreign Currency Account =
>
> SUM(\'Clients - Banking\'\[Foreign Currency Account\] )
>
> ![](media/image15.png){width="2.516884295713036in"
> height="1.4417913385826773in"}

**Engagement Account :**

> Engagement Banking is nothing but puts the customer at the center and
> aims to deliver the digital experiences they expect.
>
> Engagment Length =
>
> SUM(\'Clients - Banking\'\[Engagment Days\])
>
> ![](media/image16.png){width="2.475214348206474in"
> height="1.3584514435695538in"}

**Credit Cards Balance :**

> It is the total amount of money currently owned by a cardholder to
> their credit card bank.
>
> Credit Cards Balance = SUM(\'Clients - Banking\'\[Credit Card
> Balance\] )
>
> ![](media/image17.png){width="1.9835050306211723in"
> height="1.125097331583552in"}

**Visualization And Result --**

**Home**

![](media/image18.png){width="6.268055555555556in"
height="3.2069444444444444in"}

**Loan Analysis**

![](media/image19.png){width="6.268055555555556in"
height="3.198611111111111in"}

**Deposit Analysis**

![](media/image20.png){width="6.268055555555556in"
height="3.192361111111111in"}

**Summary Dashboard**

![](media/image21.png){width="6.268055555555556in"
height="3.158333333333333in"}

**Conclusion --**

Empowered by the latest data visualization techniques, Power BI
dashboards are among the most effective resources for using in banking
sector. As outlined in this write-up, a banking operations dashboard in
Power BI can be developed with key banking related metrics and KPIs.

**Future Work --**

With these dashboards banks can easily know what is the total loan
amount and all other things of a particular investor.

It also helps which type of banks have more number of clients as we can
see private banks have more number of clients so it can helps other
banks can build their strategies to increase clients.

It also provides insights about which nationality has highest bank
loans.

It gives information about various types of amount involved in different
types of accounts by investors.
