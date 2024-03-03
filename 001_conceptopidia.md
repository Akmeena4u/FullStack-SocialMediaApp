
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



These notes cover the server-side implementation of JWT token generation, testing, and verification, as well as a brief mention of the next steps involving client-side routing. If you have any specific questions or need further clarification, feel free to ask!
</details>


<details>
  <summary>React Router</summary>
  ### React Router Implementation:

#### Package Installation:
1. **React Router Dom Installation:**
   - Installed the `react-router-dom` package on the client side using `yarn add react-router-dom`.

#### Client-Side Implementation:

1. **Router Setup in index.js:**
   - Imported `BrowserRouter` from `react-router-dom` in the `index.js` file.
   - Enclosed the `Provider` component with `BrowserRouter`.
   - Mentioned the transition from version 5 to version 6 of React Router.

2. **Route Configuration in app.js:**
   - Imported necessary classes from `react-router-dom`: `Routes`, `Route`, `Navigate`.
   - Configured route logic in the `app.js` file.

3. **Conditional Rendering based on User Authentication:**
   - Checked user availability in the Redux store using `useSelector`.
   - Implemented route navigation based on user availability.
   - Used the `Navigate` class for navigation.
   - Routes:
      - `/`: Redirects to the home or authentication page based on user availability.
      - `/home`: Redirects to home or authentication based on user availability.
      - `/authentication`: Redirects to home or authentication based on user availability.

4. **Manual Key Clearance for Testing:**
   - Cleared localStorage keys manually to simulate a clean start for the application.

5. **Practical Testing:**
   - Demonstrated login functionality with the user "John" and tested route redirection.
   - Emphasized that testing for sign-up was not shown due to the tutorial's length.

#### Next Steps: Share Component Logic Implementation:

1. **Share Component Logic:**
   - Announced the intention to implement the logic for the Share component.
   - Desired outcome: the user should be redirected to the home page after successful login or sign-up.

These notes cover the implementation of React Router on the client side, including package installation, setup in `index.js`, and route configuration in `app.js`. Additionally, practical testing was demonstrated for the login functionality. The next steps involve the implementation of logic for the Share component. If you have further questions or need clarification, feel free to ask!
</details>



<details>
  <summary>Share post setup</summary>

steps:

Adjusting the image state in the post component.
Handling the submit functionality for uploading a new post.
Creating a new post object with user id, description, and image data.
Uploading the image to the server using an action and middleware.
Creating an API endpoint on the server for handling image uploads.
Dispatching actions for success and failure of image upload.
Implementing a reducer for managing the post state.
Handling loading and error states in the UI during post upload.
Creating a reset function to clear input fields after a successful post upload.
The next steps mentioned include fetching timeline posts based on followers and displaying both the user's posts and those of their followers.

### Image State Adjustment:
In the script, the first modification is made to the state handling the image in the post component. Instead of creating an object with a `url` property, the `url` is directly assigned to the `image` property of the state. This change simplifies the structure.

```jsx
const [image, setImage] = useState(null);

// ...

// Inside the JSX
<img src={image} alt="Preview" />

// ...

// Handling image selection
const handleImageChange = (event) => {
  const selectedImage = event.target.files[0];
  setImage(URL.createObjectURL(selectedImage));
};
```

### Submit Functionality:
A new function named `handleSubmit` is created to handle the submission of a new post. It retrieves the user's ID and description, checks if an image is selected, and creates a `FormData` object for uploading the image to the server.

```jsx
const handleSubmit = async (event) => {
  event.preventDefault();

  const userId = useSelector((state) => state.authentication.authData.user.id);
  const description = descriptionRef.current.value;
  
  if (image) {
    const data = new FormData();
    const fileName = new Date().toISOString() + selectedImage.name;
    data.append('file', selectedImage, fileName);
    // ... (dispatch action to upload image to server)
  }

  // ... (dispatch action to upload post data to server)
};
```

### Uploading Image:
An action `uploadImage` is dispatched with the image data using Redux Thunk middleware. This action utilizes the `axios` library to send a POST request to the server's upload endpoint.

```jsx
// Action Creator (uploadActions.js)
export const uploadImage = (data) => async (dispatch) => {
  try {
    await uploadApi.uploadImage(data);
    // ... (dispatch action for successful image upload)
  } catch (error) {
    console.error(error);
  }
};

// API Call (uploadApi.js)
export const uploadImage = (data) => api.post('/upload', data);
```

### Server-Side Handling:
The server-side code includes setting up a route `/upload` to handle image uploads. It utilizes the `multer` middleware to process and save uploaded images in the `public/images` directory. The image's filename is based on the current date and time.

```javascript
// Server-Side Route (uploadRoute.js)
const upload = multer({ dest: 'public/images/' });

router.post('/upload', upload.single('file'), (req, res) => {
  // ... (handling the uploaded file, e.g., saving in the database)
  res.status(201).json({ message: 'File uploaded successfully' });
});
```

### Uploading Post Data:
Another action `uploadPost` is dispatched after successful image upload to handle the creation of a new post on the server. The server-side code returns the newly created post.

```jsx
// Action Creator (uploadActions.js)
export const uploadPost = (data) => async (dispatch) => {
  try {
    const newPost = await uploadApi.uploadPost(data);
    dispatch({ type: 'UPLOAD_SUCCESS', data: newPost });
  } catch (error) {
    console.error(error);
    dispatch({ type: 'UPLOAD_FAIL' });
  }
};
```

### Post Reducer:
A reducer `postReducer` is implemented to manage the state related to post uploads. It handles actions for upload success, upload fail, and the initial state.

```jsx
// Post Reducer (postReducer.js)
const postReducer = (state = { posts: null, loading: false, error: false, uploading: false }, action) => {
  switch (action.type) {
    case 'UPLOAD_SUCCESS':
      return { ...state, uploading: true };
    case 'UPLOAD_FAIL':
      return { ...state, uploading: false, error: true };
    // ... (other cases for managing posts)
    default:
      return state;
  }
};
```

### UI Integration:
In the UI, the loading state is used to dynamically change the button text to 'Uploading...' and disable the button during the upload process. Additionally, a `reset` function is implemented to clear the image and description fields after a successful post upload.

```jsx
const loading = useSelector((state) => state.postReducer.uploading);

<button type="submit" disabled={loading}>
  {loading ? 'Uploading...' : 'Share'}
</button>

// ...

const reset = () => {
  setImage(null);
  descriptionRef.current.value = '';
};

// Called after successful post upload
reset();
```

### Timeline Posts:
The script mentions the next steps, including fetching timeline posts based on followers and displaying both the user's posts and those of their followers. However, the details for this part are not provided in the provided script.

If you have any specific questions or if there's a particular part you'd like more clarification on, feel free to let me know!
</details>

<details>
  <summary>Timeline post setup</summary>

  Certainly! Let's break down the process in more detail:

### 1. Fetching User and Posts:

In the `post.jsx` component, the `useSelector` hook from React-Redux is employed to fetch the user, posts, and loading status from the global state.

```jsx
import { useSelector } from 'react-redux';

// ...

const user = useSelector((state) => state.authReducer.authData.user);
const posts = useSelector((state) => state.postReducer.posts);
const loading = useSelector((state) => state.postReducer.loading);
```

Here, `user` holds the information about the currently logged-in user, `posts` stores an array of posts, and `loading` indicates whether the posts are still being fetched.

### 2. Fetching Timeline Posts:

A `useEffect` hook is used to trigger the fetching of timeline posts when the component mounts. It dispatches the `getTimelinePosts` action, which is responsible for fetching posts based on the user's ID.

```jsx
import { useEffect } from 'react';
import { useDispatch } from 'react-redux';
import { getTimelinePosts } from '../actions/postActions';

// ...

const dispatch = useDispatch();

useEffect(() => {
  dispatch(getTimelinePosts(user?.id));
}, [dispatch, user]);
```

### 3. Action for Fetching Timeline Posts:

In the `postActions.js` file, the `getTimelinePosts` action is created. This action dispatches actions indicating the start of fetching, successful fetching, and failure in case of an error.

```jsx
// postActions.js

export const getTimelinePosts = (id) => async (dispatch) => {
  try {
    dispatch({ type: 'FETCH_TIMELINE_POSTS_START' });
    const data = await postApi.getTimelinePosts(id);
    dispatch({ type: 'FETCH_TIMELINE_POSTS_SUCCESS', payload: data });
  } catch (error) {
    console.error(error);
    dispatch({ type: 'FETCH_TIMELINE_POSTS_FAIL' });
  }
};
```

### 4. API Request for Fetching Timeline Posts:

In the `postApi.js` file, a `getTimelinePosts` method is implemented to send a GET request to the server's endpoint for fetching timeline posts.

```jsx
// postApi.js

export const getTimelinePosts = (id) => api.get(`/post/timeline/${id}`);
```

### 5. Server-Side Handling for Fetching Timeline Posts:

On the server side, in the `postController.js` file, a new route is implemented for fetching timeline posts based on the user's ID.

```javascript
// postController.js

const getTimelinePosts = async (req, res) => {
  try {
    // Logic to fetch timeline posts based on user ID
    // ...

    res.status(200).json({ timelinePosts: /* posts data */ });
  } catch (error) {
    console.error(error);
    res.status(500).json({ message: 'Internal Server Error' });
  }
};

module.exports = { getTimelinePosts };
```

This is where you would implement the logic to fetch posts based on the user's ID. The fetched posts are then sent as a JSON response.

### 6. Displaying Timeline Posts:

In the JSX of the `post.jsx` component, the `map` function is used to iterate over the `posts` array and render each post.

```jsx
// post.jsx

return (
  <div>
    {loading ? (
      <p>Fetching posts...</p>
    ) : (
      posts.map((post) => (
        // Render each post with necessary details
        // ...
      ))
    )}
  </div>
);
```

### 7. Handling Likes and Dislikes:


</details>


<details>
  <summary>Like a Post</summary>

  Certainly, let's elaborate on the provided script:

### 1. **Initializing Like State in the Post Component:**

In the `post.jsx` component, a `useState` hook is used to manage the like-related state variables:

```jsx
import React, { useState } from 'react';

// ...

const Post = ({ data }) => {
  // ...
  const [liked, setLiked] = useState(data.likes.includes(user.id));
  const [likes, setLikes] = useState(data.likes.length);
  
  // ...
};
```

Here, `liked` represents whether the current user has liked the post, and `likes` represents the total number of likes on the post.

### 2. **Rendering Like Button and Cursor Styling:**

The JSX is modified to include a like button. The styling is adjusted to change the cursor to a pointer when hovering over the like button.

```jsx
return (
  <div>
    {/* ... other post details ... */}
    <button onClick={handleLike} style={{ cursor: 'pointer' }}>
      {liked ? 'Unlike' : 'Like'}
    </button>
    <p>{likes} {likes === 1 ? 'like' : 'likes'}</p>
  </div>
);
```

The button text dynamically changes based on whether the post is liked or not.

### 3. **Handling Like Functionality:**

The `handleLike` function toggles the like state and sends a request to the server to like or unlike the post.

```jsx
const handleLike = async () => {
  try {
    setLiked((prev) => !prev);
    const response = await postApi.likePost(data.id, user.id);
    
    if (response.data.liked) {
      setLikes((prev) => prev + 1);
    } else {
      setLikes((prev) => prev - 1);
    }
  } catch (error) {
    console.error('Error liking/unliking post:', error);
  }
};
```

This function first toggles the `liked` state locally, then sends a request to the server using `postApi.likePost`. Depending on the server's response, it updates the total number of likes (`likes` state).

### 4. **Implementing the Like Post API Request:**

In the `postApi.js` file, the `likePost` method is added to handle the API request for liking or unliking a post.

```jsx
// postApi.js

export const likePost = (postId, userId) => api.put(`/post/${postId}/like/${userId}`);
```

This method sends a PUT request to the server, specifying the post ID and user ID in the URL.

### 5. **Server-Side Handling for Liking/Unliking a Post:**

On the server side, a new route is implemented in the `postController.js` file to handle liking or unliking a post.

```javascript
// postController.js

const likePost = async (req, res) => {
  try {
    // Logic to like/unlike the post based on post ID and user ID
    // ...

    res.status(200).json({ liked: /* true/false based on like status */ });
  } catch (error) {
    console.error(error);
    res.status(500).json({ message: 'Internal Server Error' });
  }
};

module.exports = { likePost };
```

The logic inside `likePost` would typically involve updating the post in the database based on the current like status.

### 6. **Visual Feedback on Like/Unlike:**

The code provides visual feedback when a post is liked or unliked by updating the local state and the total like count accordingly.

### 7. **Testing the Like/Unlike Functionality:**

The functionality is tested by clicking the like button, observing the local state changes, and verifying the server's response through console logs.

### 8. **Next Steps:**

The script hints at additional work, such as fixing the profile card for the home page, but the details of these tasks are not provided in the given script.

This script mainly focuses on implementing the like/unlike functionality for a post in a React-Redux application, involving both client-side and server-side modifications.
</details>


<details>
  <summary>Profilecard setup</summary>
  Certainly, let's go through the provided script with more detailed code explanations.

### 1. **Profile Card Setup on Home Page:**
The `ProfileCard` component is designed to display user information, with different content based on its location (whether it's on the profile page or the home page). Here's a detailed breakdown:

```jsx
import React from 'react';
import { useSelector } from 'react-redux';
import { Link } from 'react-router-dom';

const ProfileCard = ({ location }) => {
  // Extracting user data from the Redux store
  const user = useSelector(state => state.authReducer.authData);

  // Constructing image URLs for cover and profile pictures
  const coverImage = user.coverPicture ?
    `${process.env.REACT_APP_SERVER_PUBLIC}${user.coverPicture}` :
    `${process.env.REACT_APP_SERVER_PUBLIC}default-cover.jpg`;

  const profileImage = user.profilePicture ?
    `${process.env.REACT_APP_SERVER_PUBLIC}${user.profilePicture}` :
    `${process.env.REACT_APP_SERVER_PUBLIC}default-profile.png`;

  // JSX for displaying user information
  return (
    <div className="profile-card">
      {location === 'profilePage' ? (
        // Content for the profile page
        <div>
          <img src={coverImage} alt="Cover" className="cover-image" />
          <img src={profileImage} alt="Profile" className="profile-image" />
          <h2>{`${user.firstName} ${user.lastName}`}</h2>
          <p>{user.worksAt || 'Write about yourself'}</p>
          <p>Followers: {user.followers.length}</p>
          <p>Following: {user.following.length}</p>
          {/* Add other profile-related information here */}
        </div>
      ) : (
        // Content for the home page
        <div>
          {/* Customize content as needed for the home page */}
        </div>
      )}
    </div>
  );
};

export default ProfileCard;
```

### 2. **Dynamic User Data Extraction:**
This code snippet represents a simplified version of the Redux store responsible for handling user authentication data.

```jsx
// Redux store slice for user authentication data
const authReducer = (state = { authData: null }, action) => {
  // Handle authentication-related actions
  // ...
};

export default authReducer;
```

### 3. **Display User Information:**
Within the `ProfileCard` component, user information such as name, workplace, and follower counts are displayed dynamically.

```jsx
{/* Displaying user information */}
<h2>{`${user.firstName} ${user.lastName}`}</h2>
<p>{user.worksAt || 'Write about yourself'}</p>
<p>Followers: {user.followers.length}</p>
<p>Following: {user.following.length}</p>
```

### 4. **Styling Adjustments:**
This CSS snippet ensures that the styling for `.nav-icons` and `.link` is consistent.

```css
/* Styling for nav-icons and link within the profile card */
.nav-icons, .link {
  text-decoration: none;
  color: inherit;
}
```

### 5. **Navigation to Profile Page:**
A link is wrapped around "My Profile" to enable navigation to the user's profile page.

```jsx
<span className="link">
  <Link to={`/profile/${user.id}`}>My Profile</Link>
</span>
```

### 6. **Routing Setup for Profile Page:**
In `App.js`, a route is defined to handle navigation to profile pages based on user IDs.

```jsx
// Routing setup for profile pages
<Route path="/profile/:id" exact component={ProfilePage} />
```

### 7. **Navigation to Home Page:**
In the `HomeVideo` component, an image is wrapped in a `Link` component to enable navigation to the home page.

```jsx
{/* Navigation to the Home page */}
<Link to="/home">
  <img src={homeImage} alt="Home" className="home-image" />
</Link>
```

### 8. **Post Filtering for Profile Card:**
This code snippet filters the number of posts dynamically based on the user's ID.

```jsx
// Extracting posts from the Redux store
const posts = useSelector(state => state.postReducer.posts);

// Dynamic number of posts based on the user's ID
const numberOfPosts = posts.filter(post => post.userId === user.id).length;
```

### 9. **Dynamic Number of Posts:**
The dynamic number of posts is displayed within the `ProfileCard` component.

```jsx
{/* Displaying the dynamic number of posts */}
<p>Posts: {numberOfPosts}</p>
```

### 10. **Test with New Post:**
This section demonstrates the creation of a new post for testing purposes.

```jsx
// Creating a new post for testing
const newPost = {
  title: 'REST API Tutorial',
  content: 'Learn the basics of REST API development.',
};

// Dispatching the action to add the new post
dispatch(addPost(newPost));
```

### 11. **Post Display on Profile Page:**
In the `ProfilePage` component, user posts are filtered and displayed on the profile page.

```jsx
// Extracting user data and posts from the Redux store
const user = useSelector(state => state.authReducer.authData);
const posts = useSelector(state => state.postReducer.posts);

// Filtering posts based on the user's ID
const userPosts = posts.filter(post => post.userId === user.id);
```

### 12. **Profile Card Logic for Different Pages:**
The `ProfileCard` component renders different content based on its location prop.

```jsx
// Conditional rendering based on the location prop
{location === 'profilePage' ? (
  // Content for the profile page
  // ...
) : (
  // Content for the home page
  // ...
)}
```

### 13. **Additional Notes:**
A note regarding potential internet connection issues is included.

```jsx
// Note on potential internet connection issues
// ...
```

### 14. **Post API Tutorial:**
The `addPost` function in the post API file demonstrates how to make a request to add a new post.

```jsx
// Making a request to add a new post
const addPost = async (newPost) => {
  // ...
};
```

### 15. **Post Display on Profile Page:**
The `ProfilePage` component maps through user posts and displays them.

```jsx
{/* Displaying user's posts on the profile page */}
{userPosts.map(post => (
  // Displaying post details
  // ...
))}
```

These detailed explanations provide a clearer understanding of each code snippet's purpose and functionality.
</details>
