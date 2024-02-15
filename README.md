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

- Question View: When clicking on a question, the view of this question should be displayed:
	- The name of the user who owns the question should be displayed next to their profile picture, along with the date and time of the question's creation. The question itself with the corresponding description should also be displayed.
	- If the question has been answered, all the answers should be displayed, sorted based on their score in descending order, meaning the answers with the highest score will be shown first. Each answer should be displayed with the username of the answer's owner, their profile picture, the date of the answer's creation, the answer itself, and the accumulated score of the answer.
	- If the user is logged in and has not yet answered this question, a textarea will be enabled for them to respond to the question if they wish; otherwise, the textarea will not be shown.
	- Each logged-in user can rate each of the answers within this question once, within a range of 1 to 5. When rating an answer, the option to rate that answer should be removed, and the current score of the answer should be updated using JavaScript without reloading the page.
	- If the user within the view is the owner of the question, they will have the option to mark the question as resolved when there is at least one answer. They will also have the option to delete the question as long as it has not been marked as resolved.
	- Each username displayed in this view (question and answers) should redirect the current user to the corresponding user profile when clicked.

- User Profile: Each registered user will have their user profile, where other users can see the questions asked by this user:
	- Upon accessing this view, the profile picture should be displayed, followed by the user's name, the email entered during registration, and the date this user became a member.
	- The current accumulated score of the user obtained from ratings assigned (by other users) to the user's answers should also be displayed. Additionally, the total score obtained by this user since becoming a member will be shown.
	- There will be a button that redirects to a new page where all the questions asked by this user will be found, with the most recent ones displayed first.
	- If the current user is the owner of the profile, they will have the option to change their profile picture.
	- People who have not logged in will be able to access existing user profiles in the same way.

- My Questions: This page will contain all the questions asked by a specific user:
	- The questions will be sorted based on their creation time, with the most recent ones displayed first.
	- People who have not logged in will be able to access this page in the same way, meaning this page is available to the general public.

- Home: This page will display all the questions from all users:
	- They will be sorted based on the number of views each question has in ascending order, meaning the least viewed questions will be shown first.
	- People who have not logged in will be able to access this page in the same way, meaning this page is available to the general public.

- Ask: In this section, the user can ask a new question:
	- Logged-in users can ask a new question by providing the question itself, a description, and the question's category.
	- If the current user has 20 or more points, a checkbox will be enabled, giving the user the option to highlight their question. If selected, 20 points will be deducted from the user upon publishing the question.

- Categories: This section will display all the existing categories for the questions:
	- Upon selection of this section, a page will display all the existing categories, listed one below the other.
	- Upon selecting any of these categories, all the questions assigned to this category will be displayed.
	- The questions will be sorted based on the number of views each question has in ascending order, meaning the least viewed questions will be shown first.
	- People who have not logged in will be able to access this page in the same way, meaning this page is available to the general public.

- Question Types: Every page displaying questions should show the 3 types of questions:
	- The displayed questions should respect the colors assigned to their respective question types: `#4C8891` for resolved questions, `#C9C9D0` for unresolved questions, and `#735492` (animation) for highlighted unresolved questions.

- API Calls: Every page displaying questions should:
	- Make a fetch call to retrieve all existing questions containing the required feature for the desired page.

- Pagination: Every page displaying questions should implement pagination to manage the display of a large number of questions.
	- Show a maximum of 10 questions.
	- If there are more than 10 questions, there should be a "Next" button that takes the user to the next page of questions. Similarly, if the user is not on the first page, a "Previous" button should appear to take the user to the previous page of questions.
	- The default order of the questions for the page should be maintained when switching to the previous or next page.
	- Using JavaScript, the group of questions should be deleted and the new group of 10 questions should be displayed when the user selects the previous or next option to avoid the need to reload the entire page.

Files Created

Where are they located?

- CSS: answers -> static -> answers
- HTML: answers -> templates -> answers
- JS: answers -> static -> answers

***style.css***: This file contains the design style that the application will use, including designs for buttons, text, body, and for each element used in the application, as well as the characteristic animation for highlighted questions. This file is called from the "layout.html" file, which is the base for all other HTML files, so the CSS code affects these mentioned HTML files.

***urls.py*** (application "answers"): Within this file are the URLs used for this application (_answers_), including the login, logout, and register URLs. It also contains the default URLs for responding to API calls and for rendering the views by calling the corresponding HTML file. Finally, this file contains the necessary libraries for the correct functioning.

***views.py***: Within this file are all the functions that provide specific functionality in response to requests sent to the URLs contained in the ***urls.py*** file (application "answers"). Some of the responses provided by these functions include JSON responses, views calling specific HTML files, among others. For a better understanding, the functioning of each of these functions will be explained as needed. This file also contains a function called *len_notifications*, which is responsible for returning the number of unread notifications for the current user and is called within the same file by some of the functions. Additionally, this file contains the necessary libraries for the functions (def) to perform their tasks without any issues.

***layout.html***: This is the main base file from which the rest of the HTML files will inherit the base structure, as well as the contained "script" and "stylesheet." Primarily, this file provides the navigation bar (nav), which, depending on whether the user is logged in or not, will display or hide some of the options in the navigation bar. It also provides the line <meta name="viewport" content="width=device-width, initial-scale=1.0">, which allows the application to be compatible with mobile devices. Additionally, this file provides three "blocks" to allow the rest of the HTML files to add the desired group of tags in these block sections. The first block is for the title (block title), the second is for the script (block script), and the third is for the body (block body). This file uses the designs provided by Bootstrap as the "stylesheet" for the application's design and uses the style.css file as a secondary "stylesheet." It also uses the layout.js file as the "script," the content and function of which will be explained later.

***layout.js***: This file contains the script that governs the functionality of the bottom navigation bar between the question pages. Each page displays a maximum of 10 questions, and if this number is exceeded, the code in this file allows navigation between these pages. All HTML files containing questions will display this navigation bar at the bottom and therefore can interact with this JS file.

The navigation bar (_nav_) contains different sections, and each section sends a request to a specific URL when clicked. The following sections and the corresponding URLs for the requests upon clicking will be shown (further explanation of what happens behind these requests will be provided later):

	***No login required***
	- *Home*: Clicking on it will send a GET request to the URL named _index_, which is linked to the function *def index*.
	- *Categories*: Clicking on it will send a GET request to the URL named *show_categories*, which is linked to the function *def show_categories*.
	- *Search bar*: Pressing the "*Search*" button will send a POST request to the URL named *search*, which is linked to the function *def search*.

	***Login required***
	- *Username*: This section will display the name of the current user when logged in. Clicking on it will send a GET request to the URL named _profile_, which is linked to the function *def profile*.
	- *My Questions*: Clicking on it will send a GET request to the URL named *my_questions*, which is linked to the function *def my_questions*.
	- *Ask*: Clicking on it will send a GET request to the URL named _ask_, which is linked to the function *def ask*.
*(Notifications)*: Clicking on it will send a GET request to the URL named _notifications_, which is linked to the function *def notifications*.
	- *Log Out*: Clicking on it will send a GET request to the URL named _logout_, which is linked to the function *def logout*.

	***No login required***
	- *Log In*: Clicking on it will send a GET request to the URL named _login_, which is linked to the function *def login*.
	- *Register*: Clicking on it will send a GET request to the URL named _register_, which is linked to the function *def register*.

***views.py*** (*def index*): When the URL named _index_ receives a GET request, this function calls the view linked to the file ***index.html***.

***index.html***: As mentioned earlier, this file extends the ***layout.html*** file, so it will display the navigation bar at the top of the page. Additionally, this file contains an empty *div* element with the id **div-questions** which will be used in the manipulation performed by the ***index.js*** file, which also uses this HTML file as its script.

***index.js***: This file makes an API call using the _fetch_ command to the URL named *get_questions*, which is linked to the function *def get_questions* to retrieve all the questions that have been asked by the users. Each question is placed inside the *div* element with the id **div_questions** in the ***index.html*** file. For each question, the profile picture of the user who asked the question, the user's name, the question's creation date, and the question itself are displayed.

***views.py*** (*def get_questions*): When the URL named *get_questions* receives a GET request, this function retrieves all the questions asked by the users, sorts them based on their number of views in ascending order, and returns a JSON response for each question as a response to the API call made by the ***index.js*** file.

***views.py*** (*def show_categories*): When the URL named *show_categories* receives a GET request, this function calls the view linked to the file ***categories.html***.

***categories.html***: As mentioned earlier, this file extends the ***layout.html*** file, so it will display the navigation bar at the top of the page. Additionally, this file displays the available categories for the different user questions. Clicking on any of them will send a GET request to the URL named *questions_category* (sending the corresponding category code through the request), which is linked to the function *def questions_category*.

***views.py*** (*def questions_category*): When the URL named *questions_category* receives a GET request along with the desired category code, this function calls the view linked to the file ***questions_category.html*** passing the category code as a variable to the HTML file.

***questions_category.html***: As mentioned earlier, this file extends the ***layout.html*** file, so it will display the navigation bar at the top of the page. Additionally, this file contains an empty *div* element with the id **div-questions-category** which will be used in the manipulation performed by the ***questions_category.js*** file, which also uses this HTML file as its script. This file contains a **hidden input** which has the category code as its data under *data-category*.

***questions_category.js***: This file makes an API call using the _fetch_ command to the URL named *category* linked to the function *def category*, passing the code obtained from *data-category* belonging to the **hidden input** in the ***questions_category.html*** file. When this API call is made, all the questions created for this specific category are retrieved. Each question is placed inside the *div* element with the id **div-questions-category** in the ***questions_category.html*** file. For each question, the profile picture of the user who asked the question, the user's name, the question's creation date, and the question itself are displayed.

***views.py*** (*def category*): When the URL named *category* receives a GET request with the corresponding code of the desired category, this function retrieves all the questions containing this category, sorts them based on their number of views in ascending order, and returns a JSON response for each question as a response to the API call made by the ***questions_category.js*** file.

***views.py*** (*def profile*): When the URL named *profile* receives a GET request with a username included, this function calls the view linked to the file ***profile.html***.

***profile.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file includes a structure where initially the user's profile picture is displayed. If the profile page matches the current user, the page provides the option for the user (profile owner) to change the profile picture. Below the profile picture, the page displays the profile owner's name, email, registration date and time, current score, overall score, and a button that, when clicked, makes a GET request to the URL named *my_questions*. This will redirect the current user to all the questions asked by the profile owner.

***views.py*** (*def my_questions*): When the URL named *my_questions* receives a GET request with a username included, this function calls the view linked to the file ***myquestions.html***.

***myquestions.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file contains an empty *div* element with the id **div-myquestions** which will be used in the manipulation performed by the ***myquestions.js*** file, which also uses this HTML file as its script.

***myquestions.js***: This file makes an API call using the _fetch_ command to the URL named *get_my_questions* linked to the function *def get_my_questions*, providing a username (profile owner) to retrieve all the questions asked by this user. Each question is placed inside the *div* element with the id **div_myquestions** in the ***myquestions.html*** file. For each question, the profile picture of the user who asked the question, the user's name, the question's creation date, and the question itself are displayed.

***views.py*** (*def get_my_questions*): When the URL named *get_my_questions* receives a GET request, this function retrieves all the questions asked by the provided username, sorts them showing the most recent questions asked by the user, and returns a JSON response for each question as a response to the API call made by the ***myquestions.js*** file.

***views.py*** (_def ask_): Access to this function is only possible if the user is logged in; otherwise, the user will be redirected to the login page. When a GET request is sent to this function, the file ***ask.html*** mentioned earlier is called and displayed to the user. When a POST request is sent to this function, the text value of the question and description is obtained, the chosen category is retrieved, and the value of whether the user wanted to highlight their question or not is obtained. If the user wanted to highlight their question, 20 points are deducted from the **score** attribute of the ***User*** model object representing the current user, and the update is saved. Additionally, the value of the **highlighted** attribute (Question model) will be *True*. Otherwise, no points are deducted from this user, and the value of the **highlighted** attribute (Question model) will be *False*. Once these values are obtained, a new object of the *Question* model is created, filling its attributes with this information, and the user is redirected to the URL named *my_questions* linked to the function *def my_questions*, which was previously discussed.

***ask.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file provides a user-friendly structure for the logged-in user to input their desired question in a **text input**, the description in a **textarea**, the category in a **select**, submit the **form** with a **submit button**, and if the user has 20 or more points, they can select a **checkbox** to publish a highlighted question if desired. When the form is submitted, it is sent with the POST method to the URL named **ask**.

***views.py*** (*def notifications*): When the URL named *notifications* receives a GET request with a username included, this function compares the username of the current user with the username sent in the GET request. If both names match, the view linked to the file ***notifications.html*** is called. Otherwise, a restriction message is presented to the current user, preventing users from viewing notifications of other users.

***notifications.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file contains an empty *div* element with the id **div-notifications** which will be used in the manipulation performed by the ***notifications.js*** file, which also uses this HTML file as its script.

***notifications.js***: This file makes an API call using the _fetch_ command to the URL named *get_notifications* linked to the function *def get_notifications*, providing a username to retrieve all the notifications for this user. Each notification is placed inside the *div* element with the id **div_notifications** in the ***notifications.html*** file.

***views.py*** (*def get_notifications*): When the URL named *get_notifications* receives a GET request with a username included, this function compares the username of the current user with the username sent in the GET request. If both names match, a JSON response for each notification is returned, sorting the most recent notifications. Otherwise, a restriction message is presented to the current user, preventing users from accessing notifications of other users.

***views.py*** (*def get_notification*): When the URL named *get_notification* receives a PUT request with a username and a notification ID included, this function compares the username of the current user with the username sent in the PUT request. If both names match, the notification is marked as read. Otherwise, a restriction message is presented to the current user, preventing users from marking notifications of other users as read. This function only accepts PUT requests; otherwise, a message requiring a PUT request is displayed.

***views.py*** (*def search*): When the URL named *search* receives a POST request with a textual search included in the form, this function provides this search to the *search.html* file.

***search.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file contains an empty *div* element with the id **div-results** that will be used in the manipulation performed by the ***search.js*** file, which also uses this HTML file as its script.

***search.js***: This file makes an API call using the _fetch_ command to the URL named *get_search* linked to the function *def get_search*, providing the corresponding text for the desired search. Each of the questions obtained as a result of the search is placed inside the *div* element with id **div_results** in the ***search.html*** file. For each question, the profile image of the user who asked the question, the name of this user, the date of the question creation, and the question itself are displayed.

***views.py*** (*def get_search*): When the URL named *get_search* receives a GET request with the search text included, this function retrieves all the questions containing the search text in their content, sorting each question from the least number of views to the highest number of views in ascending order. Finally, it returns a JSON response for each of the questions as a response to the API call made by the ***search.js*** file.

***register.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file contains a form where the Username, E-mail, Password, and Password confirmation are entered. When the form is submitted, it is sent with a POST method to the URL named *register*.

***views.py*** (*def register*): When the URL named *register* receives a POST request, the Username, E-mail, Password, and Password confirmation are extracted. Then it is verified that this data is not empty, if it is, an error message will be displayed. Then it is verified that the Password and the Password confirmation match, if not, an error message will also be displayed. If the above is successful, a new user will be attempted to be created, if the Username already exists, an error message will be displayed again. If everything has been done correctly, the new user will be created, the session will be started, and the current user will be redirected to the URL named *index*. When the URL named *register* receives a GET request, the fields linked to the *register.html* file are displayed.

***login.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file contains a form where the Username and Password are entered.

***views.py*** (*def login*): When the URL named *login* receives a POST request, the Username and Password are extracted. Then an authentication is performed to verify that the user with the entered data exists, if not, an error message indicating that the username or password is incorrect will be displayed. If the username and password are correct, the user's session will be started, and the user will be redirected to the URL named *index*. When the URL named *login* receives a GET request, the fields linked to the *login.html* file are displayed.

***logout.html***: When the URL named *logout* receives a GET request, the session of the current user will be closed, and the user will be redirected to the URL named *index*.

***views.py*** (*def question_view*): When the URL named *question_view* receives a GET request with the question id, this function retrieves the question containing this id, and increments its view count. Then, if a user is logged in, it attempts to retrieve the answer (from the current user) to the question linked to the id. If there is an answer from the current user to this question, a variable called *answered* is set to **True**, otherwise it is set to **False**. If no user is logged in, this variable is set to **True**. Finally, this variable is sent to the *question.html* file.

***question.html***: As mentioned earlier, this file extends the layout.html file, so it will display the navigation bar at the top of the page. Additionally, this file adds a structure where initially, if the current user is the owner of the question and the question has not been answered at least once, the option to *Delete question* will be displayed. If the question has been answered at least once and the current user is the owner of the question, the option to *Set question as resolved* will be presented. Then, the profile image of the user who asked the question, the name of the user who asked the question, the date and time when the question was asked, the question, and the question description are displayed. If the question has not been answered, a user is logged in, the current user is different from the question user, and the *answered* variable is not **False** (the current user has not answered this question), then the user will be allowed to provide an answer to the question by submitting a form to the URL named *get_answers_question* with the question id included. The way this question is marked as answered is by making a PUT request to the URL named *question*.

***views.py*** (*def get_answers_question*): Initially, the URL named *get_answers_question* retrieves the question linked to the id obtained in the request. When a POST request is received, it gets the owner of the question, extracts the response from the submitted form, and creates a new object of the ***Answer*** model with the current user, the extracted response, and the question. Then, a notification (an object of the ***Notification*** model) is created for the owner of the question with the previously obtained user, the question linked to the id, the created answer, and again the user. Once this is done, the user will be redirected to the URL named *question_view*, passing the same obtained id. When a GET request is received, all the answers containing this question (linked to the obtained id) are retrieved, and the answers are sorted by their score, starting with the highest score at the top. Finally, a JSON response is returned for each of the answers as a response to the API call made by the *question.js* file.

***question.js***: This file makes an API call using the _fetch_ command to the URL named *get_answers_question* linked to the function *def get_answers_question*, providing the corresponding id of the desired question. Each of the responses obtained as a result of the call is placed within the *ul* element with the ID **ul-answers** in the file ***question.html***. For each response, the profile image of the user who owns the response, the name of this user, the creation date of the response, the response itself, and, if a user different from the owner of the response has logged in, a set of 5 *input-radio* elements will be displayed, allowing the user to click on one of them to assign a score to this response within a range of 1 to 5. Upon selecting one of these options, this set of options is removed, and the score for this response is updated, both of which are done using JavaScript without the need to reload the page. The way in which the score of a response is updated is through an API call using the _fetch_ command to the URL named *score* with the PUT method, sending a question id and a response id. Additionally, this file also marks a question as resolved. This is done through a PUT call using the _fetch_ command to the URL named *question* (linked to the function *def question*), sending the id of the desired question. Finally, another API call is made to the URL named *get_answer*, providing the corresponding id of the response of interest. This call is made to check if the response of interest has already been scored by the current user.

***views.py*** (*def score*): This function initially retrieves the question linked to the obtained id, as well as the response that has been scored linked to the second obtained id, and finally, it retrieves the user who owns this response. If this function receives a PUT request, it extracts the corresponding scoring data, updates the score of the response by adding the current score to the previous one, adds the current user as a "rater" of this response, adds the scored points to the current user's score, and also adds this same score to the overall score of this user. Finally, a notification (an object of the ***Notification*** model) is created for the user who owns the response. If this function receives a GET request, it returns a JSON response where the response linked to the obtained id in the request is sent. This type of GET request is used to specifically obtain the score of the response and update this part without having to refresh the entire page.

***views.py*** (*def question*): When the URL named *question* receives a PUT request with the question id, this function retrieves the question containing this id. If the current user is the same user as the owner of the question (login is required for this URL), the obtained question is marked as resolved. If the current user is different from the owner of the question, this request is restricted. This function only accepts PUT requests.

***views.py*** (*def get_answer*): When the URL named *get_answer* receives a GET request with the id of the response of interest, this function retrieves that response with the id and returns a JSON response to the file where it was called (*question.js*), in order to check if this response has already been scored by the current user.

***views.py*** (*def delete*): When the URL named *delete* receives a GET request with the id of the question of interest, this function retrieves the question corresponding to this id and compares the owner of this question with the current user. If both match, the question is deleted, and the user is redirected to the URL named *my_questions*. If they don't match, a restriction message is displayed to the user; access to this URL is only allowed when logged in. This function is called by the user from the *question.html* file if desired.

***models.py***: This file contains the models created for the operation of this web application. A total of 4 models were created:
		- User: With 3 attributes (in addition to the default ones) -> image, score, overall
		- Question: With 8 attributes -> user, question, description, category, resolved, highlighted, views, timestamp		
		- Answer: With 6 attributes -> user, question, answer, score, raters, timestamp
		- Notification: With 8 attributes -> user, question, answer, read, scored, score, user_rater, timestamp

***admin.py***: In this file, the 4 models created are registered in the admin site accessible to the superuser.

***urls.py (project)***: This file includes the *urls* file corresponding to the *answers* application. Additionally, the following lines of code are added to enable the use of images:
*from django.conf.urls.static import static*
*if settings.DEBUG:*
    *urlpatterns += static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)*

***settings.py***: In this file, the *answers* application is added in the **INSTALLED_APPS** section. Additionally, the following lines of code are added to create a folder where the user images will be stored:
*MEDIA_ROOT = os.path.join(BASE_DIR, 'media')*
*MEDIA_URL = '/media/'*

***file "media"***: The "media" folder contains a subfolder named "images," where the profile images used by the users and the default images for the app's operation can be found. The default images consist of three items: the notification icon image, the default profile image, and the app's logo image.

How to run the application?

1. Initially, in order to take advantage of user creation, we will create a superuser from the terminal.

2. Next, we will run the server and create a second user in the "Register" section at the top.

3. Upon creating this second user, we will log in and proceed to ask four questions in the "Ask" section at the top, with each question being asked in a different category. As observed, each time we ask a question, the application redirects us to the "My Questions" section, so it is necessary to reselect the "Ask" section.

4. After asking the four questions, we will log out and log in with the superuser by selecting the "Log In" section at the top.

5. Upon logging in, we will be redirected to the "Home" section (at the top). In this section, we can see all the questions that have been asked by all users. Currently, there are only the four questions that we asked with the other user. We will select each question and provide an answer to each. At this point, we can notice that when we answer the question, we are redirected to the view of that question, meaning the page is refreshed, and we notice two things: our question has been published, but we are also not allowed to answer the same question again. Additionally, we have to return to the "Home" section each time we answer in order to respond to the remaining questions. At this point, we notice that the questions in this section are in a different order. This is because each time we select a question to answer or simply view it, that question receives an additional view. Questions with more views will be placed at the bottom, while those with fewer views will be placed at the top in the "Home" section.

6. When the four questions have been answered, we will log out and log in again with the other user. We notice that we have four notifications. By clicking on the notification icon, we see that all four notifications show that the other user has answered our question (user's name), displaying the question text as well. We will click on each notification and rate each of the other user's responses with a score of 5, granting 20 points to the user who responded. While we rate each response, we notice that the rating bar disappears and the response score is updated without needing to reload the page. Each time we rate, it is necessary to select the notifications again. When a notification is selected, it is marked as read, and the number of notifications for this user decreases by 1.

7. We will log out and log in with the other user again. Similarly, we see four notifications at the top. We will select the notification icon and see that each notification shows that the other user (user's name) has rated our response (response text) with a certain score (score assigned to this response). We will select one of the four notifications and be redirected to the corresponding question where our response was rated.

8. We will select the *profile section (user's name)* at the top. We will see that we can change our profile picture and do so by selecting *"Choose File,"* choosing an image, and saving it. We will see that our profile picture has changed. This section shows various data related to this user, one of which is the **Score**, representing the number of points this user currently has. Since four responses of this user were rated with a score of five, we can see that the user has a total of 20 points.

9. We will select the *Ask* section and ask a **highlighted** question. To do this, we will select the checkbox that says *"Post as highlighted (**20 points**),"* fill in the other fields, and publish the question. This option is only available if the user has a total of 20 points or more. After publishing the question, we can see that we are redirected to the *My Questions* section and notice that the question we asked has a striking color change.

10. We will select the *Home* section and see that our highlighted question is here. We will select the *Categories* section at the top and consecutively select each of the four categories. We will notice that each category contains questions that were asked under that category and are sorted by the number of views in ascending order.

11. With the current user, we will ask six more questions. We select the *Home* section, scroll to the bottom of the page, and move to page 2. As we can see, the second page only has one question, as each page contains a maximum of ten questions, and there are a total of eleven questions for the *Home* section. However, the order of the questions based on views in ascending order is still respected. This same rule applies to any section containing questions; only a maximum of 10 questions per page is allowed. It is important to note that when switching between question pages, the web page is not reloaded, thanks to a methodology using JS to prevent this.

12. We will select the notification icon and choose any notification. While viewing the question, we can click on any username on this page to be redirected to that user's profile page. In this case, we will select the username of the other user. When on this user's profile, we will click the *See questions asked* button. We see that we are redirected to the questions asked by this user. If we want to see our own questions, we simply select the *My Questions* section at the top.

13. In the search bar, we will enter a character, characters, or words that match the text content of at least one of the questions asked so far (the more matches, the better). We see that indeed all questions containing the entered text in the search are displayed, ordering the questions again based on the number of views in ascending order.

14. We log out and see that many of the functions that were performed are not possible to do with a session not initiated, such as answering questions.

15. We log in with the other user (the user who owns the answered questions). We select the notification icon and choose any notification. We notice that we have two options, the *Set question as resolved* option and the *Delete question* option. We will select the *Set question as resolved* option. Instantly, we notice that both options disappear, and if we refresh the page, this question will have the characteristic green color of a resolved question.

16. Again, we select the notification icon and choose any notification (different from the previous step). Similarly, we have the *Set question as resolved* option and the *Delete question* option. We will select the *Delete question* option. Instantly, we notice that we are redirected to the *My Questions* section and notice that the deleted question is no longer there.

17. We select the *Home* section and answer one of the other user's questions.

18. We enter the ***admin*** site in the URL and log in with the super user we created. We can select any of the four models used in this application and add, edit, or delete objects of these models to our liking. We search in the ***Questions*** model for the question answered in the previous step, select the *Resolved* checkbox, and save.

19. We return to the default URL, log out, and register a third user. We search for the question that was marked as resolved in the previous step and notice that despite not having answered with the current user to this question, it is not possible to respond because it has already been marked as resolved. However, we can still rate other users' responses. The responses with the highest accumulated score will appear first.

Additional information

- Each section containing questions will display the 3 characteristic colors that identify them, depending on the type of question: whether the question is highlighted, resolved, or not.

- Each section containing questions will only display a maximum of 10 questions per "question page"; however, when switching between "question pages", the web page does not fully reload, JavaScript was used to prevent this.
