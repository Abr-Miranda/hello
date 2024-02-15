Distinctiveness: My project is different from other projects because it consists of a web page for technological questions and answers. Each user registered on the website will be able to ask questions assigned to different technological categories. They can also answer questions from other users, and the users who view these responses can assign a score to them. This cumulative score will be used to highlight questions, which will feature a continuous and eye-catching animation that will make the question stand out from the rest.

The questions are ordered from least viewed to most viewed, so that questions that have been published for a long time appear on the first pages that most users see, increasing the probability of them being answered. When a user clicks on a question, a view is added to the question and they will be redirected to the expanded view of the question, where the description appears and where users can provide an answer.

There are 3 types of questions: unresolved questions, resolved questions, and highlighted questions. Resolved questions will appear with the color tone #C9C9D0 (white), unresolved questions with the color tone #4C8891 (green), and highlighted questions will have a continuous color change starting with the tone #735492 (purple).

The owner of the question can mark their question as resolved when it contains at least one answer. Once the question has been marked as resolved, it will change to the tone #4C8891 (applies to highlighted questions as well) and will be closed to further answers but can still be viewed. The owner of the question will also have the option to delete the question, however, once the question has been marked as resolved, it cannot be deleted. When the question is deleted, it will disappear from any place that could display it.

Each user can only respond once to each question from other users, and each user can only rate each response from other users once on a scale of 1 to 5. The cumulative score given by users to each response from other users will appear alongside the response. If a user has responded to 5 questions and received a cumulative score of 15 for each of their 5 responses, this user will have a user score of 75 points. These accumulated points can be spent when the user asks a highlighted question. Each highlighted question has a cost of 20 points, so when a user has a quantity equal to or greater than 20 points, an option will be enabled for the user to choose whether they want their question to be highlighted or not. If the user chooses to highlight the question, 20 points will be deducted from their account.

When another user responds to a question from another user, the user (owner of the question) must be notified that their question has been answered. Similarly, when another user has rated a response from another user, the user (owner of the response) must be notified that their response has been rated.

Users will be able to access the categories of the questions and select one of them to view the questions corresponding to that category. Additionally, they will be able to use a search bar where, upon entering text and starting the search, all questions containing the entered text should appear, facilitating the search for questions of interest to the user and improving the website experience.

Complexity: Part of the complexity of this project is related to the use of 4 models (Question, Answer, User, and Notification). However, in order to make the complexity of the project more understandable, I chose to create a list of all the objectives that were planned for this project. It is important to note that ALL objectives were achieved. Later on, I will explain how each of these objectives was accomplished:

- Search Bar: The application should have a search bar where users can search for questions of interest.
	- Once the user has performed a search, all questions containing the entered text should be displayed.
	- The order in which the questions are displayed should be based on the number of views each question has, in ascending order.
	- The search bar should be available for both logged-in and non-logged-in users.
	- Only POST requests to this URL will be allowed to obtain search results; otherwise, a JSON response "POST request required" will be shown.
	- Users who are not logged in should also be able to access this function, meaning the function will be available to the general public.

- Notifications: Notifications should be displayed to the user for their questions that have been answered and for their responses that have been rated.
	- When a user has answered another user's question, the latter should be notified that their question has been answered, displaying the name of the user who answered, the question to which they responded, and the date and time it was answered.
	- When a user assigns a rating to another user's response, the latter should be notified that their response has been rated, displaying the name of the user who assigned the rating, the response that was rated, the value with which this response was rated, and the date and time it was rated.
- Only logged-in users will be able to see their number of unread notifications in the navigation bar.
	- A notification will be marked as read only after the user has clicked on it.
	- When the user clicks on a notification, they should be redirected to the corresponding view of the question where the event occurred.
	- It is not possible to generate notifications for other users if the user is not logged in. If the user is logged in, the notifications generated will have the current user as the author, and it will not be possible to involve another user as the author.
