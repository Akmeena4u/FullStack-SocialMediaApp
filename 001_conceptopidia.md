
# Frontend = css+react
1. firstly i have created a react app using - yarn -> node install-> yarn  install-> yarn start  and downloaded required img ,data
2. make two blur rounded shapped circle  for corner  background  by make two div in app.js
3.  pages = my whole webpage have three pages mainly auth, home, profile
4. components =  now divided webpage into profile , home ,trending sections all componets of these section are in respective components folders , each card have .css and .jsx files
5. now my app have below folder structure
  ---
 <img width="505" alt="image" src="https://github.com/Akmeena4u/FullStack-SocialMediaApp/assets/93425334/35a2a61e-385d-4b8d-8ab4-c9bd2471fe89">
---

## componets 
---
### Home
---
![image](https://github.com/Akmeena4u/FullStack-SocialMediaApp/assets/93425334/c4730958-3561-42d5-87e2-afb63b6b4a52)

---
1. profilecard.jsx -- add cover image and profile img from img folder and using style.css styled intial profile card                                                                                                        now i settled positions of profile img AND  name using bottom = 3rem , margin-top - 3rem respectiveely
  followercard.jsx --   here initially i designed it woth hardcore data and for all buttons of followcard or other web butttons in app.js so that  i can use them globally


2. postside componet-- postshare.jsx -- add img ,input ,post options with a imported icon for photoselection use - usestate ,useref hooks
                       post card -

   *Note :- to remove scrollbar we used :-  The ::-webkit-scrollbar CSS pseudo-element affects the style of an element's scrollbar when it has scrollable overflow.*

 3. Rightside-- make icons of right side and style them
                trencard.jsx-- import trends datset from datafolder and impplemented share button

 
 ### profile-page 
 ---
 ![image](https://github.com/Akmeena4u/FullStack-SocialMediaApp/assets/93425334/b8f2cb6c-a4ef-42c7-8ff0-0559c52a0b10)

---
 profilepage - it have search bar , info bio ,who following , followers ,  logout option    
 1. profileleft.jsx -- to show effect make every class relative , it have info card  and followcard
 2. center-- profile.jsx from profilecard
 3. rightside-same as trending


### Auth-page
---
![image](https://github.com/Akmeena4u/FullStack-SocialMediaApp/assets/93425334/872eab97-fa8a-4ecf-91a2-288ed5260d20)
---
1. leftside - it have app name and tagline
2. rightside- created form for login and signup with buttons

   *Note -to edit info of profileleft  like bio and all use modal inside profilemodal.jsx compo, for this we have used maintine library's modal component , while onclicking it will fire event to 
          edit*
                         
---                   
        




# Backend 

Here we need to implement authenticity for users, timeline posts of users  and dates of postings , likes and dislikes options , crud on posts 
for above all we have to setup rest api , complex mongodb queries , request handling , perfect routing on server side 
firstly setup node project and install moomngoose ,  express ,nodemon ,

## create db - connect app with db
1. db-> browse collection -> add my own data ->deploy
2. connect moongoose in app  with required modifications and after connecting it will listen at a port
3. dotenv- install dotenv for storing secure informations and use dotenv.config and use all env files using process.env.MONGO_DB ,

## Server structuree 
1. index.js--> Routes--> auth, user,post mean its have paths to each controllers
2. model---> here we made js-schema  for all componets
----
## Routes 
### 1. auth route - controller -> model -> test api in thunderclient( collection-> new folder-> requests like registerUser and test using localhost:5000/auth/register-> body-> fill->
                we will make login and signup compos and *bcrypt* to make passwords encrypted
### 2. user/profile route --
       1. getuser- it will show password but for privacy i take away password and send them as response in user controller
       2. updateuser controller - (put) - updated in body if admins trues to update  when we wants to update passwords here error will come due to hashed password so again we needs to bcrypt 
       3. delete controller- easy(if same or admin) - delete
       4. followuser- himself cant follow and show forbidden error and if already followed then no output otherwise push updates in followers array and following array and we can check increae 
       5. unfollow - same as follow just change request as pull


### post-modal--post controller --> route
       1. create newpost- 
       2. get post by id
       3. update post- if post id is same as user id
       4. delete post- same as update
       5. like-dislike- if currebt ud is not in likes array -push and,  if exist and pushing- unlike mean pull
       6. get timeline post- self +other user who are in followings
          here we have to input others post using usermodal using aggreagte(math ,lookup intregrated )

  ---     

---

#Intergration of frontend and Backend

## Introduction:
    Overview of completing a social media application using a full-stack approach. Previous completion of the design and REST API for the platform.

## Goals for the Current Session:
    1. Integration of server and client-side.
    2. Learning client-side routing using React Router version 6.
    3. Implementing global state management with React Redux store.
    4. Bonus: Persisting store state even after page refresh.
    5. Authentication with JWT authentication tokens.
    6. Using Redux Thunk middleware for asynchronous actions.


<details>
 <summary>Improving Authentication Page</summary> 

  ### Improving Authentication Page

#### Setting Up Client-side:
1. Created a "client" folder for the frontend.
2. Initialized the client-side using `yarn start`.
3. Concurrently ran the server-side using `npm start`.
4. Opened VS Code and navigated to the "pages" directory.
5. Modified the login and signup components in the "or.jsx" file.
6. Removed the login function and utilized the signup component.
7. Structured the layout with a comment to distinguish between the left and right sides.
8. Implemented conditional rendering using the `useState` hook for login and signup forms.
9. Created a button to switch between login and signup forms based on user interaction.
10. Styled the clickable text with a pointer cursor.

#### Handling Form Inputs:
11. Initialized a `data` state with the `useState` hook to store input values.
12. Created a `handleChange` function to update the `data` state on input changes.
13. Applied the `handleChange` function to all input fields using the `onChange` attribute.
14. Changed the input type for password fields to "password" for security.

#### Confirming Passwords:
15. Added a `confirmPass` state to manage whether the confirmed password is valid.
16. Conditionally rendered an error message if the confirmed password doesn't match.
17. Styled the error message with a red color, font size, and margin.
18. Ensured the error message is displayed only when `confirmPass` is false.

#### Handling Form Submission:
19. Implemented a `handleSubmit` function to prevent default form submission.
20. Checked if the form is in signup mode and verified if the password matches the confirmed password.
21. Updated the `confirmPass` state accordingly.
22. Created a `resetForm` function to reset form values and clear error messages.
23. Called `resetForm` during the switch between login and signup modes.

#### Connecting to Backend:
24. Prepared the setup for connecting to the backend using Redux.
25. Introduced the concept of Redux for global state management.

</details>
