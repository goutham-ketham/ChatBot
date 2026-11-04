# React Chatbot

A simple, interactive chatbot application built using React and Vite. The application provides a chat interface where users can send messages and receive responses from a chatbot powered by the `supersimpledev` package.

## Live Demo

[View the Live Chatbot](https://goutham-ketham.github.io/ChatBot/)


## Features

- Interactive chatbot interface with separate user and robot messages.
- Send messages using the Send button or the Enter key.
- Clear the input field using the Escape key.
- Loading indicator while the chatbot generates a response.
- Automatic scrolling to the latest conversation.
- Responsive chat layout with user and robot profile images.
- Production-ready build generated using Vite.

## Tech Stack

| Technology | Purpose |
|---|---|
| React 19 | Building the user interface |
| Vite 6 | Development server and production build |
| JavaScript | Application logic |
| HTML5 | Application structure |
| CSS3 | Styling and layout |
| supersimpledev | Chatbot response generation |
| Git & GitHub | Version control and hosting |
| GitHub Pages | Application deployment |

## Project Structure

```text
chatbot-project/
├── public/
│   └── vite.svg
├── src/
│   ├── assets/
│   │   ├── robot.png
│   │   └── user.png
│   ├── components/
│   │   ├── ChatInput.jsx
│   │   ├── ChatInput.css
│   │   ├── ChatMessage.jsx
│   │   ├── ChatMessage.css
│   │   ├── ChatMessages.jsx
│   │   └── ChatMessages.css
│   ├── App.jsx
│   ├── App.css
│   ├── index.css
│   └── main.jsx
├── dist/
│   ├── assets/
│   └── index.html
├── index.html
├── package.json
├── package-lock.json
├── vite.config.js
├── eslint.config.js
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

Make sure you have the following installed:

- Node.js (a recent LTS version is recommended)
- npm
- Git

Check your installations:

```bash
node -v
npm -v
git --version
```

### Installation

1. Clone the repository:

```bash
https://github.com/goutham-ketham/ChatBot.git
```

2. Navigate to the project directory:

```bash
cd ChatBot
```

3. Install the dependencies:

```bash
npm install
```

4. Start the development server:

```bash
npm run dev
```

5. Open the local URL displayed in the terminal, usually:

```text
http://localhost:5173/
```

## Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Starts the Vite development server |
| `npm run build` | Creates the production build in the `dist` directory |
| `npm run preview` | Serves the production build locally |
| `npm run lint` | Runs ESLint to check the code |

To test the production build locally:

```bash
npm run build
npm run preview
```

## How It Works

### 1. Application Initialization

The `App.jsx` component maintains the chat conversation using React's `useState` hook.

The initial conversation is empty. The application displays a welcome message until the user sends their first message.

### 2. Sending Messages

The `ChatInput.jsx` component manages the text input and handles user interactions.

When a message is sent:

1. The application checks whether the input is empty or a response is already being generated.
2. The user's message is added to the conversation.
3. A loading indicator is displayed.
4. The chatbot response is requested asynchronously.

### 3. Generating Chatbot Responses

The application uses the `Chatbot.getResponseAsync()` method from the `supersimpledev` package.

```javascript
const response = await Chatbot.getResponseAsync(inputText);
```

The returned response is added to the conversation and displayed in the chat interface.

### 4. Rendering Messages

The `ChatMessages.jsx` component renders the conversation by mapping over the message array.

The `ChatMessage.jsx` component displays each message with the appropriate user or robot profile image.

### 5. Automatic Scrolling

The chat interface uses React's `useEffect` and `useRef` hooks to automatically scroll to the latest message whenever the conversation changes.

## Deployment

This project was deployed using GitHub Pages.

### Understanding the `dist` Folder

When you run:

```bash
npm run build
```

Vite compiles the React application into static HTML, CSS, and JavaScript files and places them in the `dist` directory.

The `dist` directory contains the production version of the application. It is different from the original source code in the `src` directory.

The deployed application does not require React source files or `node_modules` to be hosted on GitHub Pages.

### Deployment Method 1: Uploading the `dist` Contents

The first deployment was performed by uploading the contents of the `dist` folder directly to the GitHub repository.

This allows GitHub Pages to serve the built application as a static website.

The deployment process is:

1. Run `npm run build`.
2. Open the generated `dist` directory.
3. Upload the contents of `dist` to the GitHub repository.
4. Configure GitHub Pages to deploy from the appropriate branch and folder.
5. Open the deployment URL provided by GitHub.

### Deployment Method 2: Uploading the Complete Project

The complete project was subsequently uploaded to the GitHub repository, including the React source code, configuration files, dependencies manifest, and the generated `dist` directory.

This allows the repository to contain both the original source code and the production build.

For this project, the Vite configuration contains:

```javascript
export default defineConfig({
  plugins: [react()],
  base: "/ChatBot/",
});
```

The `base` option configures the application to use the `/ChatBot/` path when deployed under a GitHub Pages project repository.

**Important:** If you change the repository name, update the `base` value in `vite.config.js` to match the new repository name before generating a new production build.

For example, if the repository is named `my-chatbot`, use:

```javascript
base: "/my-chatbot/",
```

Then rebuild the application:

```bash
npm run build
```

### Recommended Deployment Workflow

For future updates, keep the complete source project in your GitHub repository and use the following workflow:

```bash
git add .
git commit -m "Update chatbot application"
git push
```

If you are deploying the `dist` directory directly, regenerate the production build whenever you change the source code.

Alternatively, configure GitHub Pages to build and deploy the application automatically using GitHub Actions. This removes the need to manually upload the contents of `dist` after every update.

## Limitations

- The chatbot response generation depends on the `supersimpledev` package.
- The application currently uses a basic chat interface without user authentication.
- Conversation messages are maintained in React state and are not saved permanently.
- The project does not include a custom backend or database.
- Chatbot responses depend on the behavior and availability of the response-generation package.

## Future Improvements

- Add persistent conversation history using local storage or a database.
- Improve the interface for mobile devices.
- Add support for multiple conversations.
- Add error handling for failed chatbot requests.
- Add a typing indicator and improved loading animations.
- Implement automatic deployment using GitHub Actions.

## Author

**Goutham Ketham**

GitHub: [Goutham-Ketham](https://github.com/goutham-ketham)

## License

This project is available for educational and personal use. Add a license file to the repository if you want to specify formal permissions for reuse and distribution.
