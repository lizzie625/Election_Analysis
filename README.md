# Election_Analysis

##Overview
Assisting Tom- CO board of elections employee- in an election audit of tabulated results. We have been tasked to report total # votes cast, total votes for each candidate, % votes for each candidate, and election winner based on popular vote. This project can be done in excel but we will not be using excel since you can automate the process with python. We have generated a vote count report for Tom and Seth, with 3 different voting methods (mail in ballots, punch card, DRE counting machines) taken into account. The code we created can be used for other with other election data in the future, as well. 

##Resources Used
Data Source: election_results.csv
Software: Python 3.7.6; Visual Studio Code, 1.63.2

##Analysis
#First Look at the Data
The first thing we had to do was inspect the electin_results.csv data we were given, which can be found in the "Resources" folder. Looking at this data we can see that there are 3 different variables: Ballot ID, Coutny, and Candidate. There are 369, 712 rows of data, including the header. We need to use python in Visual Code Studio to efficiently sift through the data, rather than scrolling through all of it on excel. 
#Loading the Data
We first load the election_results.csv file so that we can open and read the file. This can be done directly or indirectly, in our final code it is done indirectly. We also needed to write data to a file so that the final results will be shown on a text file that we can then send to the election commission. We created a folder named analysis which will contain a text file with the result output. This can be seen in lines 8-14 of PyPoll.py along with the variables they have been assigned. We created a for loop to go through the rows of data from the .csv file, not including the header row to determine vote count per candidate. 
#Determining Votes and Candidates
To count up all of the votes (total_votes) we initialized an accumulator, which will increase the value by 1 for each row read in the for loop we created. We declared a new list (candidate_options) to pull the candidate name as we go through each row. WE know the candidate name is listed in the 3rd column, or 2nd index, of the data and assign it as such within our for loop. We then created an if statement to eliminate candidate names being repeated.
#Determining votes per candidate
We declared an empty dictionary (candidate_votes) and placed it below our candidate_options list. We then created a key for the dictionary inside the if statement. We set the candidate votes for each candidate to 0 so that we could begin tracking the votes for each candidate when we run our code.In order for the votes to continuously be counted towards a candidate we wrote code to add 1 vote to each candidate's vote count when their name is read. This code is in the for loop but not inside the if statement, if it was, the count would remain 1, rather than adding up the counts. 
#Vote Percentages
In order to determine the percentage of votes each candidate got, we need to create another for loop. The for loop retreives the number of votes each candidate received, calculates the percentage of the votes, and prints the name and vote percentage to the hundreth decimal place. 
We then create an if statement inside the for loop to determine the winning candidate, count, and percentage. This statement determines if the votes are more than the winning count, if they are, then the winning count is set to equal votes and the winning percentage is set to equal the vote percentage. We then add a print statement to print the winning candidates name, number of votes, and percentage of votes. 

###Results
The total number of votes received in the election is 369,711. The three candidates who received votes were Charles Casper Stockham, Diana DeGette, and Raymon Anthony Doane. Charles Casper Stockham received 85,213 votes. Diana DeGette received 272,892 votes. Raymon Anthony Doane received 11,606 votes. The percentage of votes each candiate got were 23.0%, 73.8%, and 3.1% respectively. Diana DeGette won the election, receiving 73.8% of the vote and 272,892 total votes

##Challenge Overview

##Challenge Summary
