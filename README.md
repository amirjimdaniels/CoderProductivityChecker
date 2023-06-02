# testRepo

Instructions:
1. Download the testPython.py file from the repository.
2. Make sure you have the PyGitHub package installed on your system. You can install it using pip install PyGitHub.
3. Open a terminal window and navigate to the directory where you have saved the testPython.py file.
4. Run the script using the command python testPython.py.
5. The script will prompt you to enter the GitHub username and the repository name for which you want to retrieve the developer metrics.
6. Enter the required information and press enter.
7. The script will fetch the required information and display it in a readable format in the console.

My solution utilizes the PyGitHub api to access metadata related to a developer's contribution to a Github repository. I chose a few metrics that I considered to be useful for determining developer productivity: Number of commits, Number of reviews commented on, Number of issues resolved, as well as the total number of lines of code added and deleted. I chose these metrics because they were easily quantifiable and had a direct correlation to how much work a developer might be doing. 


Limitations:
While these metrics are useful I think of them more as the first step to proper assessment of productivity. These metrics do not account for code-reviews completed outside the github framework as well as any work done in the planning phase. This framework also doesn't accurately measure the productivity of developer's who pair-wise program frequently and therefore is missing that additonal context. (I personally experienced this with the repository used to test my code as we utilized the Xtreme Programming process model.) If I were to describe the tool and its application to a software development context, I would state that the tool is a 2-dimensional image of the 3d dimensional process that is Software Development. While the tool does give you knowledge about the process (2 dimensions specifically) it misses out on the 3rd dimension of planning and writing quality code. 

I tried to account for this by weighing the contributions differently. Issues resolved and Reviews commented on demonstrate a more active state of contribution to the project that commits do so I awarded more points to developers for participating in code reviews and resolving issues than commits. Commits were still awarded with points however.  While lines of code added is a useful metric for seeing developer activity on a repository, I found it to be a poor judge of productivity, thus it wasn't counted in the points. For exmaple: A developer could add 7000 lines and be later forced to delete 5000 of those lines and would be judged as a more productive member of the repository than a developer who only added 1000 lines of code, but whose lines were not deleted and was persistent code that did not need to be changed.


Potential Improvements:


1. Add additional points for commented code. Well documented code has a higher likelihood of persistence and maintainability. This would add additional metrics to assess quality of code as well. 

2. The current MVP determing system is simplistic and could be better improved by adding additional metrics to make it a more comprehensive view of dev productivity. 

3. Potentially linking software to external tracking tools such as JIRA or monday.com in order to get more metrics and data to base points off of. 

4. dding support for other metrics that can help to assess developer productivity, such as the number of pull requests opened or closed, the time taken to resolve issues, and the number of tests written.

5. Developing a user interface that allows users to input the GitHub username and repository name in a more user-friendly way.

6. Adding the ability to retrieve metrics for multiple developers at once and comparing their productivity.

7. Implementing caching or other optimization techniques to speed up the data retrieval process.


Upkeep of program and Simplification for non-devs:

To ensure accuracy of data over time, it is important to regularly update the data and to account for changes to the data schema. The PyGitHub API can be used to retrieve the most up-to-date data, and versioning can be used to account for changes to the API.

In addition, data cleaning and validation can be performed to ensure that the data is consistent and accurate. This could involve removing duplicate entries, verifying that the data is in the expected format, and checking for outliers.

What you can do to make the output usable by an audience of non-technical consumers:

To make the output usable by non-technical consumers, the data should be presented in a clear and concise manner. This could involve using charts or graphs to visualize the data, or presenting the data in a table with clear headings and descriptions.

It is also important to provide context for the data, such as explaining what each metric represents and how it relates to developer productivity.


How I Approached the Problem:

I started by reviewing the requirements and identifying the key metrics that I would need to retrieve from the GitHub API. I then researched the PyGitHub package and familiarized myself with its capabilitie
Upkeep of program and Simplification for non-devs:
To ensure accuracy of data over time, it is important to regularly update the data and to account for changes to the data schema. The PyGitHub API can be used to retrieve the most up-to-date data, and versioning can be used to account for changes to the API.

In addition, data cleaning and validation can be performed to ensure that the data is consistent and accurate. This could involve removing duplicate entries, verifying that the data is in the expected format, and checking for outliers.

What you can do to make the output usable by an audience of non-technical consumers:

To make the output usable by non-technical consumers, the data should be presented in a clear and concise manner. This could involve using charts or graphs to visualize the data, or presenting the data in a table with clear headings and descriptions.

It is also important to provide context for the data, such as explaining what each metric represents and how it relates to developer productivity.
Initially, I planned to retrieve all the required data using the get_contributors_stats() method provided by PyGitHub. However, I soon realized that this method only provides high-level statistics for the entire repository, rather than detailed metrics for individual developers.

As a result, I pivoted my approach and decided to retrieve the required data by making calls to the GitHub API using PyGitHub's get_user() and get_repo() methods. This allowed me to retrieve more detailed metrics for individual developers, which could then be aggregated and presented in a more meaningful way.

One interesting technical aspect of the solution is the use of PyGitHub's pagination feature to retrieve large volumes of data in a more efficient manner. This involved making multiple requests to the GitHub API and iterating over the results until all the required data had been retrieved.

Another interesting design aspect is the use of a scoring system to assign weights to the different metrics based on their relative importance. This allowed me to calculate an overall productivity score for each developer, which could then be used to compare their contributions to the repository.



