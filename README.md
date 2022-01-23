# Election_Analysis

## Overview
Assisting Tom- CO board of elections employee- in an election audit of tabulated results. We have been tasked to report total # votes cast, total votes for each candidate, % votes for each candidate, and election winner based on popular vote. This project can be done in excel but we will not be using excel since you can automate the process with python. We have generated a vote count report for Tom and Seth, with 3 different voting methods (mail in ballots, punch card, DRE counting machines) taken into account. The code we created can be used for other with other election data in the future, as well. 

## Resources Used
Data Source: election_results.csv  
Software: Python 3.7.6; Visual Studio Code, 1.63.2

## Analysis
### First Look at the Data  
The first thing we had to do was inspect the electin_results.csv data we were given, which can be found in the "Resources" folder. Looking at this data we can see that there are 3 different variables: Ballot ID, Coutny, and Candidate. There are 369, 712 rows of data, including the header. We need to use python in Visual Code Studio to efficiently sift through the data, rather than scrolling through all of it on excel. 
### Loading the Data  
We first load the election_results.csv file so that we can open and read the file. This can be done directly or indirectly, in our final code it is done indirectly. We also needed to write data to a file so that the final results will be shown on a text file that we can then send to the election commission. We created a folder named analysis which will contain a text file with the result output. This can be seen in lines 8-14 of PyPoll.py along with the variables they have been assigned. We created a for loop to go through the rows of data from the .csv file, not including the header row to determine vote count per candidate. 
### Determining Votes and Candidates  
To count up all of the votes (total_votes) we initialized an accumulator, which will increase the value by 1 for each row read in the for loop we created. We declared a new list (candidate_options) to pull the candidate name as we go through each row. WE know the candidate name is listed in the 3rd column, or 2nd index, of the data and assign it as such within our for loop. We then created an if statement to eliminate candidate names being repeated.
### Determining votes per candidate  
We declared an empty dictionary (candidate_votes) and placed it below our candidate_options list. We then created a key for the dictionary inside the if statement. We set the candidate votes for each candidate to 0 so that we could begin tracking the votes for each candidate when we run our code.In order for the votes to continuously be counted towards a candidate we wrote code to add 1 vote to each candidate's vote count when their name is read. This code is in the for loop but not inside the if statement, if it was, the count would remain 1, rather than adding up the counts. 
### Vote Percentages
In order to determine the percentage of votes each candidate got, we need to create another for loop. The for loop retreives the number of votes each candidate received, calculates the percentage of the votes, and prints the name and vote percentage. We then create an if statement inside the for loop to determine the winning candidate, count, and percentage. This statement determines if the votes are more than the winning count, if they are, then the winning count is set to equal votes and the winning percentage is set to equal the vote percentage. We then add a print statement to print the winning candidates name, number of votes, and percentage of votes. 

# Module 3 Challenge  
## Challenge Overview
The election commission has requested that we also determine the voter turnout for each county, the percentage of votes from each county out of the total count, and the county with the highest turnout. We will use the same .csv file for this analysis.
## Methods
Given the starter code, we initialized a county list (county_options) to hold the names of the counties in the data and a dictionary(county_votes). WE then created a string to help us track the largest county and county voter turnout. We already had a for loop with the election results data inside, we added code into the for loop that allowed us to get the county name from each row. We then added another if statement inside the for loop. It states that if a county name is not yet in the county options, it will be added. We can then begin tracking each county's vote count, adding a vote to the count for every loop. We then wrote another for loop, this one needed to get the county from its respective dictionary, retrieve the county vote count, and calculate the percentage of votes for each county. We then printed these results and saved them to our text file. We wrote an if statement in our new for loop, this time to determine which couty had the largest voter turnout and what its vote count was. We saved the result to the same text file.  
![county_forloop](https://user-images.githubusercontent.com/96501958/150663749-8cf95b55-2a59-4aca-8cc0-75a865e425af.png)  

## Results
How many votes were cast in this congressional election?
  + 369,711 votes  
Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.  
  + The votes came from 3 different counties: Jefferson, Denver, and Arapahoe. Arapahoe county had the least amount of votes (24,801), making up 6.7% of the total votes. Jefferson county had 10.5% of the votes, or 38,855 votes. Denver county had the largest number of votes, making up 82.8% of the total votes and a vote count of 306, 055.  
Which county had the largest number of votes?  
  + Denver  
Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.  
  + The three candidates who received votes were Charles Casper Stockham, Diana DeGette, and Raymon Anthony Doane.   
  + Charles Casper Stockham received 85,213 votes, 23.0% of total votes.  
  + Diana DeGette received 272,892 votes, 73.8% of total votes.  
  + Raymon Anthony Doane received 11,606 votes, 3.1% of total votes.  
Which candidate won the election, what was their vote count, and what was their percentage of the total votes?  
  + Diana DeGette won the election, receiving 73.8% of the vote and 272,892 total votes  
![results_terminal](https://user-images.githubusercontent.com/96501958/150663903-257669c6-17d9-4a04-b9fe-759d5b4dcf1c.png)  
![results_txt](https://user-images.githubusercontent.com/96501958/150663906-49a59f3c-2c95-4757-9caf-6b42f5030e6d.png)  

## Challenge Summary  
We performed an analysis for the CO Board of Elections Commitee to determine various calculations from the given election data. We used python in Visual Studio Code to sift through the data and effeciently find: the winner of the election, votes and percentage of votes received for each candidate, the county with the largest voter turnout, and the voter turnout/ percent turnout of each county in the data. To do this we used for loops, decision statements, and f-strings to have the computer calculate the results we were looking for and output the results into a text file to give to the Elections Committee. This code can be used again in future elections by making some minor modifications. For one, you would need to adjust the file names to be sure you are pulling from the right data and saving to the right location.  This code can also be used for bigger elections, if you were to switch out counties for states, this script could be used for a national election.  If so, it would be able to pull the candidates vote count and percentage, as it does currently. It would also be able to determine which states had the best voter turnout. If the data had additional columns, such as party affilliation, early voting, or voting method; you can use the code written to analyze differnt data. Instead of looking at voter counts for candidates in each county/state, you could determine the voting method used. 
