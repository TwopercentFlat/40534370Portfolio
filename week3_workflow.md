## Workflow

# Choosing a Task and Preparing for Work

To start working on a task we select one from our task board in the "To do" section and move it into the "In Progress" section. We also make sure to assign ourselves to the task so that the team knows who is working on it.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Workflow/Workflow1.PNG)
![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Workflow/Workflow2.PNG)

Within the task it provides the details of what needs to be done for the task setting out most of the requirements you need to meet in order to complete the task following DOD (definition of done). These are usually represented by user stories detailing features a user would need to complete a task within the application.

To start, within your IDE you should checkout the most recent developmenmt branch to ensure you are working with current changed. Afterwards from this branch create a new branch (following our naming convention it should be "feature#n" where n is the issue number assigned on git). This is the branch where changes you make wil be commited to and prevent the master and develop branch from being changed with faulty code or bad code smell.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Workflow/Workflow3.PNG)


# Completion of Work and Creating a Pull Request

Example pull request: (https://github.com/AloiSan/UndacBlue/pull/41)

Once you have completed the task as defined within the description make sure to rebase your branch onto the latest version of the dev branch as to make sure the code doesn't have problems when combined with the current development branch after other team members have implemented their changes.

Once rebased commit your changes and push it with your new feature branch onto the remote repo. And once done created a PR (pull request). A pull request is a request to commit changes made on one branch onto another.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Workflow/Workflow4.PNG)

This request is reviewed by other team members to ensure the code is up-to-standard and of good quality. Team members will comment on the PR to establish recommended changes and if it meets the requirements set out. Examples of changes would be better comments/names, removal of duplicate code, etc.

![image](https://github.com/TwopercentFlat/40534370Portfolio/blob/main/images/Workflow/Workflow5.PNG)

# Additions Going Forward

To improve upon the given process we could make use of automated commit messages or automatic task movement to mark their stages. This would remove much of the work from picking up a task, describing changes, and changing the task state on the kanban board, improving the workflow.