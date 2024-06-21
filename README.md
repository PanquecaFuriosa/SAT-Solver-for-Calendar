# SAT solver problem

The objective of this project is to learn how to model a problem in CNF, and how to use a SAT solver to solve it, as well as translate the output of the SAT solver into a readable format.
Not only will the implementation work, but also the efficiency of its translation into CNF of the problem.

# Problem to solve

Imagine that you are organizing a tournament, and you are asked to make a program that finds a date and time assignment in which the games are going to occur. The rules are the following:

* All participants must play twice with each of the other participants, once as "visitors" and once as "homes". This means that if there are 10 teams, each team will play 18 times.
* Two games cannot occur at the same time.
* A participant can play at most once per day.
* A participant cannot play as a "visitor" on two consecutive days, nor as a "home" player on two consecutive days.
*All games must start "on the dot" (for example, 13:00:00 is a valid time but 13:30:00 is not).
*All games must occur between a specified start date and end date. Games may occur on these dates.
*All games must occur between a specified time range, which will be fixed for all days of the tournament.
*For practical purposes, all games last two hours.

# Input format

Your system should receive a JSON in the following format (assume you will always receive the correct format):

```
{
 "tournament_name": String. Tournament name,
 "start_date": String. Tournament start date in ISO 8601 format,
 "end_date": String. End date of the tournament in ISO 8601 format,
 "start_time": String. Time from which games can occur each day, in ISO 8601 format,
 "end_time": String. Time up to which games can occur each day, in ISO 8601 format,
 "participants": [String]. List with the names of the participants in the tournament
}
```

Assume that all times come with no time zone specified, and therefore assume that your time zone is UTC.

# Activity 1

They must create a translation of the problem into CNF format, and then they must create a program, in the programming language of their choice, that translates any JSON in the proposed format to the representation of the problem in [DIMACS CNF] format (https: //people.sc.fsu.edu/~jburkardt/data/cnf/cnf.html)

# Activity 2

Using the transformation created in the previous part, the files in DIMACS CNF format can be used as input for the SAT solver [Glucose](https://www.labri.fr/perso/lsimon/glucose/). You must create a program, in the programming language of your choice, that translates the output of Glucose when solving the problem into a file with the same tournament name and `.ics` extension, in [iCalendar](https ://en.wikipedia.org/wiki/ICalendar) so that it is possible to add the assignment of the games to a calendar manager. To do this you can use any library you consider necessary. Calendar events must occur at the assigned time, complying with all given rules, and must indicate who the participants in the game are, who is the "home" and who is the "away."

# Activity 3

You must create a client that handles the entire process. That is, receive a JSON in the input format, run the program that transforms it into CNF, enter the result into Glucose, and ensure that the .ics file with the response is created, or fail if it is UNSAT. You should generate easy and difficult test cases and measure the performance of your solution.

# To submit the assignment

They should have a repository with all the code used and a report describing their solution, their experimental results, as well as specific instructions for executing the entire process.

# Requirements
- Python
  
# How to install the project:
1. Run the git command below:
```
git clone https://github.com/PanquecaFuriosa/SAT-Solver-for-Calendar
```
2. Install all dependecies with the next command:
```
pip install -r requirements.py
```

# How to run the project
1. Run the bash command below:
```
python main.py
```
