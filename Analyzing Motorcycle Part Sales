/*
Analyzing Motorcycle Part Sales

Skills used: CASE Statements, Aggregate Function, Type Casting, Rounding, Filtering Rows, Grouping Rows , Sorting Rows

*/


SELECT product_line,

/*
1 -- Here, I used the EXTRACT function to determine the numerical representation of the month. Then, with the CASE statement, I ensured that the output reflects the month satisfying the corresponding condition.
*/

    CASE WHEN EXTRACT('month' from date) = 6 THEN 'June'
        WHEN EXTRACT('month' from date) = 7 THEN 'July'
        WHEN EXTRACT('month' from date) = 8 THEN 'August'
    END as month,
    warehouse,

/*
2 -- I calculated the net revenue. I converted the resulting sum with SUM to NUMERIC and rounded it to two decimal places.
*/

    ROUND(SUM(total * (1 - payment_fee))::numeric, 2) AS net_revenue
FROM sales

/*
3 -- Here, by specifying the desired client_type with WHERE, I organized the outcome using the GROUP BY and ORDER BY functions.
*/

WHERE client_type = 'Wholesale'
GROUP BY product_line, warehouse, month
ORDER BY product_line, month, net_revenue DESC
