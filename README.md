# Responsive Chatbot UI

This project provides a responsive chatbot user interface (UI) that can be embedded into a website. The chatbot includes features such as a floating button to open/close the chat, message input with send functionality, and a file upload option. The UI is built with HTML, CSS, and JavaScript.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Customization](#customization)
- [Scripts](#scripts)
- [File Upload Handling](#file-upload-handling)
- [License](#license)

## Features

- Floating button to open and close the chatbot.
- Responsive design that adapts to different screen sizes.
- Preloaded initial messages in the chat body.
- Input field for user messages with "Enter" key support for sending messages.
- Select dropdown to choose the model type.
- File upload functionality with server-side handling.
- Smooth scrolling to the latest message.

## Installation

To use this chatbot UI on your website, follow these steps:

1. **Clone the Repository**
    ```sh
    git clone https://github.com/yourusername/responsive-chatbot-ui.git
    cd responsive-chatbot-ui
    ```

2. **Include the HTML in Your Webpage**
    Copy the HTML structure from the `index.html` file provided in this repository and paste it into your webpage where you want the chatbot to appear.

3. **Add the CSS**
    Ensure the CSS provided in the `<style>` tags is included in your webpage's `<head>` section or in an external CSS file.

4. **Add the JavaScript**
    Ensure the JavaScript provided in the `<script>` tags is included at the end of your webpage's `<body>` section or in an external JS file.

## Usage

After including the provided HTML, CSS, and JavaScript in your webpage, the chatbot UI should be ready to use. Here's a brief overview of the main functionalities:

- **Opening the Chatbot**
    Click the floating chatbot button at the bottom-right corner to open the chat window.

- **Sending Messages**
    Type a message in the input field and press "Enter" or click the send button to send the message.

- **File Upload**
    Click the paperclip icon to upload a file. The selected file will be sent to the server for processing.

## Customization

You can customize the chatbot UI by modifying the following:

- **CSS Styles**
    Adjust the styles in the `<style>` section to change the appearance of the chatbot.

- **Initial Messages**
    Edit the `initialMessages` array in the JavaScript to change the preloaded messages.

- **Model Types**
    Update the options in the `<select>` dropdown to include different model types as per your requirements.

## Scripts

### `toggleChatbot()`

Toggles the visibility of the chatbot window.

### `handleKeyPress(event)`

Handles the "Enter" key press to send a message.

### `sendMessage()`

Sends the user message and appends a bot response after a delay.

### `appendMessage(text, className)`

Appends a message to the chat body with the specified class name.

### `scrollToBottom()`

Scrolls the chat body to the bottom to show the latest message.

### `uploadFile()`

Handles file upload functionality by sending the file to the server.

## File Upload Handling

The file upload functionality requires server-side handling to process the uploaded files. The example provided uses a POST request to `/upload` with `FormData`. Ensure your server endpoint `/upload` is correctly set up to handle file uploads and respond appropriately.

### Example Server-Side Handling (Node.js)

```js
const express = require('express');
const multer = require('multer');
const app = express();
const upload = multer({ dest: 'uploads/' });

app.post('/upload', upload.single('file'), (req, res) => {
  const modelType = req.body.model_type;
  // Process the uploaded file and model type
  res.json({ message: `File received and processed with model type ${modelType}` });
});

app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```
