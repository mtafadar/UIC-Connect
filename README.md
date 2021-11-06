# UIC-Connect 

# Authors

**Hina Khalid, Mosrour Tafadar and Khang Tuan Naguyen**


# Overview

## Description
This is an app which is simple version of snapchat.  UIC-students can login/sign up  with  their UIC email and see what's their fellow  students  posting about classes, life in general. Since this is simple version of snapchat there won't be any functionality to direct msg  one another. Furtheremore,  user has freedom to share their daily activities  in story where other user can see it. 



### 		App Evaluation

- **Category:**  Blogs/ Entertainment

- **Mobile:** This app  primarily developed for smartphones, but could be extended to  computers


- **Story:** To connect the  UIC students  with freedom where they can post about their  daily life  activities. Moreover, they  can post their picture and  story about their classes. This app is open to all students 



- **Audience:**  This app is  made for specific audience. In order to use the app they must be  UIC students/alumni. 


- **Habit:**  This apps can be use daily or weekly or monthly.  There are no requirement  how long a user can use it.  If an user create an account it will be there.  They can login with the email as long as they know their email and password


## 1. User Stories (Required and Optional)

**Required or must have stories**

* Logging Screen for user, with option to create new account
* User can change their password
* User will have freedom to put a display picture
* User will be able to see their fellow user stories.
* User will be able to share their own  stories.
* User can  change stories from one user to another.
* User will have option to log off 
* User will have option go back from stories main screen 

**Optional stories**

* When a fellow user posted nice picture or thought provoking ideas, the user should have freedom to reply to the story with emoji or text.
* User wants to chat with other person and by selecting message they both will be able to communicate with each other. 


## Screen  ArcheTypes

* Log in screen: 
	* Allowes user to create an account.
	* Allows user to  login to their existing account.
	* Allowes user to reset their password  if they  forget their password. 
	



* Home Screen: 
	* Allowes  user see other user stories.
	* Able to share own stories  or view the existing stories.
	     

* Profile: 
     * User can  update their profile picture
     * User can update their name
     * User can update their  email address
     * User can update  their interest of subject/major of the study
     * user can update current semester classes. 
	

# Wireframes 
	
[App Wireframe.pdf](https://github.com/mtafadar/UIC-Connect/files/7489925/App.Wireframe.pdf)



![Screen Shot 2021-11-06 at 12 01 01 AM](https://user-images.githubusercontent.com/57551265/140598617-db04b533-e2d3-44cf-ad6a-f2cab65209e7.png)


## Schema

### User Story

| Property.     | Type.         | Description.                                 |
| ------------- | ------------- | -------------------------------------------- |
| userId.       | String        | unique id for the user post (default field). |	     
| image.        | File.         | Story (image) that user posts.	       |
| caption       | String        | Story (image) caption by author	       |
| createdAt     | DateTime      | date when post is created (default field).   |
				               |

## Networking

List of network requests by screen

• Home Feed Screen:
	•(Read/GET) Query all posts where user is author.
	
	
        let query = PFQuery(className:"Post")
	query.whereKey("author", equalTo: currentUser)
	query.order(byDescending: "createdAt")
	query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
  	if let error = error { 
    	  print(error.localizedDescription)
  	} else if let posts = posts {
      	print("Successfully retrieved \(posts.count) posts.")
  	// TODO: Do something with posts...
  	 }
       }
       
•(Create/POST) Create a new comment on a story.
	•(Delete) Delete existing comment or story.
	•(Create/POST) Create a new comment on a story.
	•(Delete) Delete existing comment or story.
	
• Create Post Story Screen:
	•(Create/POST) Create a new post object.
	
• Profile Screen:
	•(Read/GET) Query logged in user object.
	•(Update/PUT) Update user profile image.


	


