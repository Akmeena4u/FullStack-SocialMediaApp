
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


<details>
  <summary>Setting up Redux</summary>

---
  ![image](https://github.com/Akmeena4u/FullStack-SocialMediaApp/assets/93425334/2ef8f5e8-d284-4507-bcb1-a514dbb57d26)

---  

**Redux Setup Steps:**

1. Navigate to the `client` folder and install the required packages using the following command:
   ```bash
   npm install redux redux-thunk react-redux
   ```

2. Import the `useDispatch` hook from `react-redux` for later use:
   ```javascript
   import { useDispatch } from 'react-redux';
   ```

3. Set up the `useDispatch` hook:
   ```javascript
   const dispatch = useDispatch();
   ```

4. Use the `dispatch` hook to interact with Redux actions. For example, in a form submission:
   ```javascript
   if (data.password === data.confirmPass) {
       dispatch(signUpAction(data)); // dispatching the signUpAction with form data
   } else {
       setConfirmPassword(false);
       dispatch(loginAction(data)); // dispatching the loginAction with form data
   }
   ```

5. Create action files inside the `actions` folder in the `client/src` directory.

6. Inside the `authActions.js` file, export and define actions such as login and signUp:
   ```javascript
   // authActions.js
   export const loginAction = (formData) => {
       return async (dispatch) => {
           // Make API call and dispatch appropriate actions based on the result
       };
   };

   export const signUpAction = (formData) => {
       return async (dispatch) => {
           // Make API call and dispatch appropriate actions based on the result
       };
   };
   ```

7. Create an `api` folder in the `client/src` directory.

8. Inside the `api` folder, create a `request.js` file and install the `axios` package:
   ```bash
   npm install axios
   ```

9. Configure the `request.js` file for making API requests:
   ```javascript
   // request.js
   import axios from 'axios';

   const api = axios.create({
       baseURL: 'http://localhost:5000', // Set your server's base URL
   });

   export default api;
   ```

10. Inside the `authApi.js` file (inside the `api` folder), define functions for login and signUp API requests:
    ```javascript
    // authApi.js
    import api from './request';

    export const login = (formData) => {
        return api.post('/auth/login', formData);
    };

    export const signUp = (formData) => {
        return api.post('/auth/register', formData);
    };
    ```

11. Create a `reducers` folder in the `client/src` directory.

12. Inside the `reducers` folder, create an `authReducer.js` file and define the authentication reducer:
    ```javascript
    // authReducer.js
    const initialState = {
        authData: null,
        loading: false,
        error: false,
    };

    const authReducer = (state = initialState, action) => {
        switch (action.type) {
            case 'AUTHENTICATION_START':
                return { ...state, loading: true, error: false };
            case 'AUTHENTICATION_SUCCESS':
                return { ...state, authData: action.data, loading: false, error: false };
            case 'AUTHENTICATION_FAIL':
                return { ...state, loading: false, error: true };
            default:
                return state;
        }
    };

    export default authReducer;
    ```

13. Create an `index.js` file inside the `reducers` folder to combine all reducers:
    ```javascript
    // index.js
    import { combineReducers } from 'redux';
    import authReducer from './authReducer';

    const reducers = combineReducers({
        auth: authReducer,
        // Add other reducers here if needed
    });

    export default reducers;
    ```

14. Create a `store` folder in the `client/src` directory.

15. Inside the `store` folder, create a `reduxStore.js` file for setting up the Redux store:
    ```javascript
    // reduxStore.js
    import { createStore, applyMiddleware, compose } from 'redux';
    import thunk from 'redux-thunk';
    import reducers from '../reducers';

    const saveToLocalStorage = (state) => {
        try {
            const serializedState = JSON.stringify(state);
            localStorage.setItem('profile', serializedState);
        } catch (error) {
            console.error('Error saving to localStorage:', error);
        }
    };

    const loadFromLocalStorage = () => {
        try {
            const serializedState = localStorage.getItem('profile');
            if (serializedState === null) return undefined;
            return JSON.parse(serializedState);
        } catch (error) {
            console.error('Error loading from localStorage:', error);
            return undefined;
        }
    };

    const persistedState = loadFromLocalStorage();

    const middleware = [thunk];

    const store = createStore(
        reducers,
        persistedState,
        compose(
            applyMiddleware(...middleware),
            window.__REDUX_DEVTOOLS_EXTENSION__
                ? window.__REDUX_DEVTOOLS_EXTENSION__()
                : (f) => f
        )
    );

    store.subscribe(() => saveToLocalStorage(store.getState()));

    export default store;
    ```

16. Finally, integrate the Redux store with the React application in the `client/src/index.js` file:
    ```javascript
    // index.js
    import React from 'react';
    import ReactDOM from 'react-dom';
    import { Provider } from 'react-redux';
    import store from './store/reduxStore';
    import App from './App';

    ReactDOM.render(
        <Provider store={store}>
            <App />
        </Provider>,
        document.getElementById('root')
    );
    ```

These steps should guide you through setting up Redux in your React application. Ensure that you customize the API endpoints and
reducers according to your project structure and requirements.


</details>


<details>
  <summary>Authenticating a user</summary>

  Certainly! Here are detailed notes based on the provided transcript:

### Server-Side Changes:

1. **Cross-Origin Issue Resolution:**
    - Encountered a "strict origin when cross-origin" error during an attempt to make a request for user registration.
    - Installed the `cors` package using `npm i cors` to handle cross-origin requests.
    - Configured the server in `index.js` to use the `cors` middleware.

2. **User Registration:**
    - Made a request to register a new user named "John" with a username "john@gmail.com" and password "john".
    - Utilized the network tab to observe the request and encountered the CORS issue.
    - Resolved the CORS issue by installing and configuring the `cors` package on the server side.

3. **Password Hashing:**
    - Integrated the bcrypt library to hash passwords.
    - Modified the server-side logic in the `authController.js` file to hash the incoming password from the request body.

4. **Duplicate Username Check:**
    - Implemented a check to verify if the provided username already exists before attempting to register a new user.
    - Used the `userModel` to find an existing user with the given username.
    - If an existing user is found, returned a response with a 400 status and a message indicating that the username is already registered.

### UI Changes:

1. **Loading State in UI:**
    - Updated the UI to display a "Loading" message when a request is pending.
    - Used React Redux hooks (`useDispatch` and `useSelector`) to manage the loading state.
    - Modified the UI buttons to show loading state dynamically based on the loading variable.

2. **Button Styling and Clickability:**
    - Introduced a CSS class called `.button-disabled` to make buttons visually distinct when disabled.
    - Made buttons unclickable by setting `pointer-events: none` in the `.button-disabled` class.
    - Dynamically applied the `.button-disabled` class to buttons based on the loading state.

3. **LocalStorage Verification:**
    - Checked the browser's localStorage to verify that user profile data is stored after a successful login or signup.
    - Showed that the data stored in localStorage includes a "profile" key, which contains user information.

### JWT Implementation:

1. **Introduction:**
    - Discussed the importance of implementing JSON Web Tokens (JWT) on the server side.

2. **Server-Side JWT Integration:**
    - Opened the `authController.js` file to make changes for JWT implementation.
    - Removed unnecessary code for extracting username and password from the request body.

### Testing:

1. **Registration Testing:**
    - Attempted to register a user to test the server's response.
    - Encountered a 400 status response due to a pre-existing username, indicating that the duplicate username check is functional.

2. **Issues and Resolutions:**
    - Encountered and resolved an error related to using an undefined `password` variable in the `authController.js` file.
    - Successfully resolved the issue, and the server ran properly.


</details>


<details>
  <summary>JWT setup</summary>

  Certainly! Here are detailed notes based on the provided transcript:

### Server-Side JWT Implementation:

1. **Package Installation:**
    - Installed the `jsonwebtoken` package on the server side using `npm i jsonwebtoken`.

2. **JWT Token Generation (User Registration):**
    - After saving a new user, implemented JWT token generation.
    - Used the `jsonwebtoken` library's `sign` method.
    - Created a token using the user's username and id, with a predefined secret key and expiration time (1 hour).
    - Stored the secret key in the server's `.env` file to keep it secure.

3. **Response with Token and User Data:**
    - Sent a response containing the new user data and the generated token.
    - Stored the token and user data in both localStorage and the Redux store.

### Client-Side Implementation:

1. **Registration Testing:**
    - Tested registration by signing up with a new user (e.g., "Eric").
    - Received a response with the new user data and an associated token.

2. **Redux Store Update:**
    - Checked the Redux store's authentication data, which now includes the user data and token after successful registration.

3. **Login Route Implementation:**
    - Implemented a login route in the server to handle login requests.
    - If the password decryption is not valid, responded with a 400 status and the message "Wrong password."
    - If valid, responded with a 200 status and sent the user data and token in the response JSON.

4. **Token Verification:**
    - Verified the generated token by testing the login functionality with an existing user (e.g., "John").
    - Received a response with the user data and token, indicating successful JWT token authentication.

### Next Steps: Routing Implementation on the Client Side:

1. **Routing Discussion:**
    - Mentioned the need to implement client-side routing for further application development.
    - Recognized the importance of navigating between different views in a single-page application (SPA).

2. **Task Ahead:**
    - Indicated that the next task involves implementing client-side routing.

These notes cover the server-side implementation of JWT token generation, testing, and verification, as well as a brief mention of the next steps involving client-side routing. If you have any specific questions or need further clarification, feel free to ask!
</details>
