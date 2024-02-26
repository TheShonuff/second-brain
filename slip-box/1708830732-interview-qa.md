---
id: 1708830732-interview-qa
aliases:
  - Interview Q&A
tags: []
---

# Interview Q&A

- **How would you go about debugging a software issue related to an autonomous vehicle?**
    - verify the issue. Mount software where the error occurred and check relevant module for the error.
    - Mount an older release and validate if the error persists.
        If yes there's a potential hardware issue.
        If no there's a potential software issue.
    - File a bug in buganizer.

- **Describe a time where you had to use data analysis and modeling to solve a problem?**
    - There was an instance where multiple non-sds Vehicle cleaning work orders where being generated. Created a SQL query on that pulled offline units that were blocking capabilities with the work orders titles. The query included a time stamp of when the unit lost capabilities. I then created another SQL query that pulled those vehicle id's and went they went back online.
    - I was able to highlight the confusion multiple different work orders was causing and show how long the units were offline with some precision.

- **Talk about a time where you had to be creative in order to find a solution to a difficult problem?**

- **Describe a situation where you had to make a decision quickly and accurately under pressure?**
    - We recently had a unit that was scheduled to leave within 12 hours to head to Detroit for E3 upfit. The vehicle lost capabilities due to a kuiper issue and was getting diagnosed. In order for the E3 upfit to be successful there can be no issues with the vehicle. I had to make the decision to quickly substitute the vehicle that was leaving in 48 hours and notify the teams coordinating the vehicle movements that we needed additional time to fix the vehicle.

- **What is the biggest issue or challenge that Waymo or other self-driving car companies are facing right now?**
    - Public acceptance.
    - Government regulation.


## Program Management
- **What Key Performance Indicators (KPIs) would you track for a system you're improving? Can you tell me an example of a KPI you'd track at Waymo**
	- RO capability vs Target
	- Offline repair times
	- Frequency of Work Orders being generated IE BFL Harness.

## Data Visualization 
- **How can one effectively illustrate data that spans many dimensions?**
- **In Python, how do you fabricate a matrix following the Benoulli distribution, and then normalize by each column's sum?**
- **Can you demonstrate how to create a normal distribution of 1000 data points with a mean of x and variance of y in R, perform a statistical summary, and plot the density? Follow this by executing the same in Python using the Codility Platform.**

## Behavioral Questions
- How do you deal with ambiguity?
- Share with me a time when you disagreed with a team member?
- Can you give an example of a time when you changed a process based on feedback from you team and how did you manage the change?
- Tell me about a time you struggled to meet a deadline?
- So far, what has been you biggest accomplishment?
    - Working up from a Fleet Technician to Fleet Manager
- Can you share an experience where you faced failure and how you overcame it?
- Share an experience where you received negative feedback?
