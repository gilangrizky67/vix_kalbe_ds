--select * from case_study_customer
--Query 1
SELECT *
FROM case_study_customer csc 
WHERE "Marital Status" IN ('Married', 'Single');

select "Marital Status", avg(age) as rata_rata_umur
from case_study_customer
WHERE "Marital Status" IN ('Married', 'Single')
group by "Marital Status";

select *
from case_study_customer csc 


--Query 2
SELECT
    CASE
        WHEN gender = 0 THEN 'Wanita'
        WHEN gender = 1 THEN 'Pria'
    END AS jenis_kelamin,
    AVG(age) AS rata_rata_umur
FROM case_study_customer csc 
GROUP BY jenis_kelamin;


select * 
from case_study_transaction cst 

select *
from case_study_store css 

--Query 3

CREATE TABLE combined_table_store_transaction AS
SELECT
    case_study_transaction.*,
    case_study_store.storename,
    case_study_store.groupstore
FROM
    case_study_transaction
INNER JOIN
    case_study_store  ON case_study_transaction.storeid = case_study_store.storeid;

   
select *
from combined_table_store_transaction

select storename, sum(qty) as total
from combined_table_store_transaction
group by storename
order by total desc

--Query 4
select storename, sum(totalamount) as total_amount
from combined_table_store_transaction
group by storename
order by total_amount desc

select *
from case_study_product csp 

--Query 5

CREATE TABLE combined_table_transaction_product AS
SELECT
    case_study_transaction.*,
    case_study_product."Product Name"
FROM
    case_study_transaction
INNER JOIN
    case_study_product  ON case_study_transaction.productid = case_study_product.productid;
   
 select *
 from combined_table_transaction_product 

select "Product Name", sum(totalamount) as total_amount
from combined_table_transaction_product
group by "Product Name"
order by total_amount desc


select "Product Name", sum(qty) as total_qty
from combined_table_transaction_product
group by "Product Name"
order by total_qty desc












