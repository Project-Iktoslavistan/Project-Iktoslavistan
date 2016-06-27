# Databases and tables
We store the data in MySQL databases. There are a few different tables:
* citizens
* time
* companies 
* criminal records
* medical records

# Citizens
Citizens have the following attributes:
* age:            amount of years someone has been in the server (one month = a year in Iktoslavistan), 10 when starting
* name:           name, changable for a little money
* id:             discord user ID
* address:        randomly generated address
* employment:     job, `unemployed` by default
* birthday:       amount of milliseconds someone joined after the start of the current 30 day period
* sex:            `m` or `f`: male or female, can't be changed
* status: 	  possible values: alive, deceased, imprisoned, deported

if a player leaves the server, that counts emigration and their records are kept for 5 months (5 in-world years)

mysql> DESCRIBE citizens;

| Field      | Type         | Null | Key | Default | Extra |
|:-----------|:-------------|:-----|:----|:--------|:------|:
| name       | varchar(64)  | YES  |     | NULL    |       |
| sex        | char(1)      | YES  |     | NULL    |       |
| birthday   | varchar(42)  | YES  |     | NULL    |       |
| address    | varchar(100) | YES  |     | NULL    |       |
| id         | varchar(20)  | YES  |     | NULL    |       |
| age        | varchar(4)   | YES  |     | NULL    |       |
| profession | varchar(100) | YES  |     | NULL    |       |
| status     | varchar(20)  | YES  |     | NULL    |       |

# Time
This table contains the absolute Iktoslavistanic epoch (since the unix epoch), what year it is (a year is a period of 30 real-life days) and the relative epoch (amount of milliseconds inbetween the current period of 30 days and the unix epoch)

| Field     | Type                | Null | Key | Default | Extra |
|:----------|:--------------------|:-----|:----|:--------|:------|;
| ab_epoch  | bigint(20) unsigned | YES  |     | NULL    |       |
| rel_epoch | bigint(20) unsigned | YES  |     | NULL    |       |
| year      | int(10) unsigned    | YES  |     | NULL    |       |


# Companies
Companies have the following attributes:
* owner(s): IDs of the people who own the company
* name: name of the company
* employee(s): IDs of the people employed by the company

if a player is in the employee(s) field of a company, but in the citizen table their profession is still `unemployed` they have to pay a small fee 

# Criminal records
List of crimes committed

# Medical records
List of all medical issues the character had
