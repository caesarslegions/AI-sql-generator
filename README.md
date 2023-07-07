
## Overview

This project is a unique blend of AI and database technologies. Leveraging TypeScript, JavaScript, and the OpenAI API, we've created an intelligent chatbot for a web application. The primary goal is to allow users to input prompts to the chatbot, which will interpret the prompts and generate corresponding SQL queries. This simplifies the process of writing complex SQL queries and can prove beneficial for both beginners and professionals by increasing productivity and efficiency.

## Code Structure

The application is based on React and encompasses both frontend and backend components.

### App.tsx

`App.tsx` is the main file of this application. It is a React component that manages the state of user messages and chat data. It also contains methods for handling API interactions and controlling chat functionalities.

Here's a brief overview of the key elements in `App.tsx`:

#### States:

- `value`: Holds the current value of the input field.
- `chat`: Contains an array of chat messages. Each message is an object that includes `role` and `content`. `role` can be "user" or "assistant", while `content` contains the message text.

#### Methods:

- `getQuery`: An async function that sends a POST request to the local server at `http://localhost:8000/completions`. The user's message forms the body of the request. After the request, it updates the `chat` state with the user's message and the API's response.
- `clearChat`: Clears the chat and the input field by resetting the `value` and `chat` states.
- `filteredUserMessages`: Contains an array of user messages filtered from the `chat` state.
- `latestCode`: Contains the latest message from the assistant.

#### Components:

- `MessagesDisplay`: A component that renders the user messages.
- `CodeDisplay`: A component that displays the latest code (SQL Query) provided by the assistant.

## Running the Application Locally

To run the application locally, ensure `npm` is installed. The frontend and backend can be started by executing the following commands:

```bash
npm run start:frontend
npm run start:backend
```

The frontend will run on http://localhost:3000 and the backend server will operate on http://localhost:8000. After both servers are up and running, visit http://localhost:3000 in the web browser to start interacting with the chatbot.

Note: The OpenAI API key and other configurations must be correctly set in the backend code for the application to operate correctly. Remember, always keep your API keys secure and avoid exposing them in the frontend code or version control systems.

#### Further Development:

Future development could include enhanced error handling, particularly for the getQuery function, to provide more robust user feedback when an API call fails. Additionally, consider adding more functionalities to handle diverse API responses, expanding beyond the generation of SQL queries.
