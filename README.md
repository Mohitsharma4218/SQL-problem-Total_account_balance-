# SQL-problem-Total_account_balance-

Consider the following table 'Transactions' that stores the account transactions for various account holders:

CREATE TABLE Transactions (
AccountNumber INT,
AccountHolderName VARCHAR(255),
TransactionDate DATE,
TransactionType VARCHAR(255),
TransactionAmount DECIMAL(10, 2)
);

INSERT INTO Transactions (AccountNumber, AccountHolderName, TransactionDate, TransactionType, TransactionAmount)
VALUES
(1001, 'Mohit Sharma', '2023-07-01', 'Deposit', 5000),
(1001, 'Mohit Sharma', '2023-07-05', 'Withdrawal', 1000),
(1001, 'Mohit Sharma', '2023-07-10', 'Deposit', 2000),
(1002, 'Pravhakar Das', '2023-07-02', 'Deposit', 3000),
(1002, 'Pravhakar Das', '2023-07-08', 'Withdrawal', 500),
(1003, 'Neeraj', '2023-07-04', 'Deposit', 10000),
(1003, 'Neeraj', '2023-07-09', 'Withdrawal', 2000);


PROBLEM_STATEMENT:- write an SQL query in the comments below that will display the total account balance for each account number and account holder name.
----------------------------------------------First try your self and then check answer query-------------------------------------

SELECT
  AccountNumber,
  AccountHolderName,
  SUM(CASE WHEN TransactionType = 'Deposit' THEN TransactionAmount ELSE -TransactionAmount END) AS TotalBalance
FROM
  Transactions
GROUP BY
  AccountNumber, AccountHolderName
ORDER BY
  AccountNumber;




