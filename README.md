# Project-20-SQL-Commands-PostgreSQL
These are assignments given in Patika Java Intermediate course.

The queries are done on the dvdrental example database that PostgreSQL provided.

## Tasks

- List all the values from the first_name columns in the actor and customer tables.

- List the intersecting values from the first_name columns in the actor and customer tables.

- List the values from the first_name column in the actor table that are not in the customer table.

- Perform the first three queries for repeated values as well.


## Queries

```sql

-- Active: 1721726315493@@localhost@5432@dvdrental@public

-- TASK 1 
(SELECT customer.first_name 
FROM customer)
INTERSECT
(SELECT actor.first_name
FROM actor); -- 72 rows

-- TASK 2
-- EXCEPT 1
(SELECT actor.first_name 
FROM actor)
EXCEPT
(SELECT customer.first_name
FROM customer); -- 56 total

-- EXCEPT 2
(SELECT customer.first_name 
FROM customer)
EXCEPT
(SELECT actor.first_name
FROM actor);-- 519 total row

(SELECT customer.first_name 
FROM customer)
UNION ALL
(SELECT actor.first_name
FROM actor); -- 799 = 2*INTERSECT + EXCEPT1 + EXCEPT2

-- TASK 3
(SELECT customer.first_name 
FROM customer)
INTERSECT ALL
(SELECT actor.first_name
FROM actor); -- 72 rows 

(SELECT actor.first_name 
FROM actor)
EXCEPT ALL 
(SELECT customer.first_name
FROM customer); -- 128 rows

(SELECT customer.first_name 
FROM customer)
EXCEPT ALL
(SELECT actor.first_name
FROM actor); -- 527 rows 

```

## Tables

### Table 1
``` 
72 rows total

Christian
Kenneth
Ray
Dustin
Tim
Karl
Grace
Jane
Audrey
Lisa
Susan
Anne
Michael
Mary
Kevin
Rita
William
Renee
Henry
Natalie
Dan
Jim
Michelle
Minnie
Christopher
Tom
Gregory
Mae
Helen
Sandra
Sidney
Jeff
Gene
Ellen
Ian
Kim
Ben
Chris
Joe
Fred
Jennifer
Carmen
Bob
Laura
Jon
Daryl
Jessica
Johnny
Harvey
Walter
Gary
Gina
John
Alan
Debbie
James
Julia
Kirk
Judy
Lucille
Ralph
Sean
Adam
Albert
Emily
Greg
Frances
Angela
Warren
Matthew
Richard
Russell

```



### Table 2
```
56 rows total for first query

Bela
Olympia
Cameron
Uma
Sylvester
Spencer
Humphrey
Fay
Burt
Thora
Cuba
Penelope
Jada
Zero
Greta
Alec
Meg
Woody
Liza
Scarlett
Milla
Cate
Salma
Rip
Vivien
Meryl
Harrison
Cary
Nick
Bette
Rock
Laurence
Geoffrey
Jude
Ed
Val
Will
Parker
Jayne
Elvis
Whoopi
Morgan
Jodie
River
Sissy
Groucho
Julianne
Oprah
Mena
Reese
Al
Kirsten
Goldie
Charlize
Angelina
Ewan

```