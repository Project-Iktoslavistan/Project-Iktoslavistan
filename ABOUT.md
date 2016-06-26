# Databases and tables
We store the data in databases. There are a few different tables:
* citizens
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
* birthday:       date the person joined

if a player leaves the server, that counts emigration and their records are kept for 5 months (5 in-world years)

# Companies
Companies have the following attributes:
* owner(s): IDs of the people who own the company
* name: name of the company
* employee(s): IDs of the people employed by the company
