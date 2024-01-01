/*
Hotel Operations Data Cleaning

Skills used: CASE Statements, COALESCE Function, Regular Expression Matching, Type Casting, Logical Operators, Arithmetic Operations, Column Aliasing

*/



SELECT id,

/*
1 -- In this context, since the data can only be 'EMEA', 'NA', 'LATAM', 'APAC', it should be 'Unknown' for other cases, which is why I entered this input.
*/

CASE
WHEN Location IN ('EMEA', 'NA', 'LATAM', 'APAC') THEN Location ELSE COALESCE (location, 'Unknown')
END AS Location,

/*
2 -- Here, since the hotel room number can be between 1 and 400, but in other cases, '100' should be entered, I entered this input.
*/

CASE
WHEN total_rooms BETWEEN 1 AND 400 THEN
total_rooms
ELSE COALESCE (total_rooms, '100')
END AS total_rooms,

/*
3 -- Here, I took 1.5 times the total_rooms for empty values, following the information provided by the exercise.
*/

COALESCE(staff_count, total_rooms * 1.5),

/*
4 -- Here, we cannot directly convert the 'opening_date' input with CAST because it contains text like '-'. Therefore, I instructed to convert 'opening_date' to 'INTEGER' if it has a numeric sequence. For the remaining part, that is, replace the empty value with '2023'."
*/

CASE
WHEN opening_date ~ E'^\\d+$' THEN CAST(opening_date AS INTEGER)
ELSE '2023'
END AS opening_date,

/*
5 -- Here, if it does not have a value of 'Leisure' or 'Business', I replaced it with 'Leisure', following the directive.
*/

CASE
WHEN target guests NOT IN ('Leisure', 'Business')
THEN 'Leisure'
ELSE target_guests
END AS target_guests
