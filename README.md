# PDF Text Extraction and Translation Website

A React-based application that allows users to upload PDF files, extract text content, and translate it from English to Spanish using i18next.

## Project Overview

This project demonstrates the capabilities of AI-assisted development using Cline to build a functional website with the following features:
- PDF file upload functionality
- Text extraction from the uploaded PDF
- Translation of the extracted text between English and Spanish
- Clean, responsive UI

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Cline Configuration](#cline-configuration)
4. [Plan vs. Act Mode](#plan-vs-act-mode)
5. [Development Workflow](#development-workflow)
6. [Project Implementation](#project-implementation)
7. [Running the Application](#running-the-application)

## Prerequisites

Before starting, ensure you have the following tools installed:

- [Node.js](https://nodejs.org/) (14.0.0 or later)
- [npm](https://www.npmjs.com/) (6.14.0 or later)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Cline Extension for VS Code](https://cline.bot/)

## Installation

1. Install Visual Studio Code if you haven't already:
   - Download from [https://code.visualstudio.com/](https://code.visualstudio.com/)
   - Follow the installation instructions for your operating system

2. Install the Cline Extension:
   - Open VS Code
   - Go to Extensions (Ctrl+Shift+X or Cmd+Shift+X)
   - Search for "Cline"
   - Click "Install"
   - Follow the setup instructions to authenticate the extension

3. Additional VS Code Extensions (Optional but Recommended):
   - ESLint
   - Prettier
   - React Developer Tools

## Cline Configuration

According to the [Cline documentation on prompting](https://docs.cline.bot/improving-your-prompting-skills/prompting), effective `.clinerules` files should provide clear context and goals. Following these guidelines, create a `.clinerules` folder in your project root with content like:

```
ai-assisted-build-a-website/
└── .clinerules/
    ├── 00-role.md       # Cline Agent - role
    └── 01-project.md    # Cline Agent - project requirements
```

00-role.md
```
Role: You are an experienced React developer with expertise in building web applications with file upload capabilities, PDF processing, and internationalization.

Goals:
1. Create a user-friendly interface for uploading PDF files
2. Extract text content from uploaded PDFs
3. Implement translation functionality using i18next
4. Ensure responsive design and good user experience
```

01-project.md
```
Technical Requirements:
- React (version 18+)
- PDF.js for PDF text extraction
- i18next and react-i18next for translation (requires React hooks support)
- Vite for build tooling

Project Structure:
ai-assisted-build-a-website/
├── public/
│   ├── locales/           # Translation files
│   │   ├── en/
│   │   └── es/
├── src/
│   ├── components/
│   │   ├── FileUpload.jsx
│   │   ├── TextDisplay.jsx
│   │   ├── TranslationPanel.jsx
│   ├── services/
│   │   ├── pdfService.js  # PDF extraction logic
│   │   ├── i18n.js        # i18next configuration
│   ├── App.jsx
│   ├── main.jsx
├── .clinerules             # Cline agent rules
├── package.json
└── README.md

Important Context:
- The application should be intuitive for non-technical users
- PDF extraction should handle documents of various sizes and complexity
- Translation should maintain formatting and paragraph structure
- The UI should provide clear feedback during processing steps

Implementation Details:
1. PDF Upload:
   - Support for drag-and-drop functionality
   - Clear indication of upload status and progress
   - File type validation to ensure only PDFs are accepted

2. Text Extraction:
   - Use PDF.js to parse PDF content
   - Handle multi-page PDFs appropriately
   - Display extracted text in a readable format
   - Show loading indicator during extraction process

3. Translation:
   - Configure i18next with English and Spanish language support
   - Implement language switching functionality
   - Translate both UI elements and extracted PDF text
   - Maintain text formatting during translation when possible

4. User Interface:
   - Clean, modern design with responsive layout
   - Accessible design following WCAG guidelines
   - Clear visual feedback for all user actions
   - Error handling with user-friendly messages

Best Practices:
- Use React hooks for state management
- Implement proper error handling
- Follow component-based architecture
- Ensure responsive design for mobile compatibility
- Write semantic HTML
- Use CSS modules for component styling

```

These cline rules help Cline understand the project requirements, technology stack, and desired structure, enabling it to provide more accurate and relevant assistance.

## Plan vs. Act Mode

According to [Cline's official documentation](https://docs.cline.bot/exploring-clines-tools/plan-and-act-modes-a-guide-to-effective-ai-development), Cline provides two distinct operational modes that are optimized for different stages of the development process:

### Plan Mode

Plan Mode is designed for the conceptual and architectural phases of development. In this mode, Cline focuses on helping you:

- Brainstorm project architecture and system design
- Plan component structure and data flow
- Make high-level decisions about libraries, frameworks, and approaches
- Understand complex concepts through detailed explanations
- Analyze requirements and identify potential challenges

Plan Mode is conversational by nature, allowing you to engage in back-and-forth discussions to refine your ideas before committing to code.

**Recommended Model for Plan Mode**: Reasoning/Thinking Models
- Excellent reasoning and planning capabilities
- Strong at explaining complex concepts
- Efficient for architectural discussions
- Good at identifying potential issues early in development

### Act Mode

Act Mode transitions from planning to execution. As described in the Cline documentation, this mode enables Cline to:

- Write and generate actual code
- Implement features based on the plan
- Execute commands in your development environment
- Debug issues and fix bugs
- Create, modify, and organize files in your project

In Act Mode, Cline can use tools like file operations, command execution, and browser interaction to help implement your application.

**Recommended Model for Act Mode**: Models Good at Coding (e.g., Claude Sonnet 3.7)
- Superior code generation capabilities
- Strong at implementing complex logic
- Excellent at debugging and problem-solving
- Efficient at translating requirements into working code

### Model Selection Resources

- [LLM Leaderboard (artificialanalysis.ai)](https://artificialanalysis.ai/) - This resource provides up-to-date comparisons of various language models across different tasks, helping you choose the most appropriate model for your specific needs. The leaderboard evaluates models on reasoning, coding, and other capabilities relevant to software development.

- [OpenRouter](https://openrouter.ai/) - OpenRouter simplifies access to multiple AI models through a single API key. Instead of managing separate accounts and API keys for different model providers, OpenRouter allows you to access a wide range of models with a unified interface. To use this service:
  1. Create an account on OpenRouter
  2. Generate an API key with credits
  3. Configure Cline to use your OpenRouter credentials
  4. Access any supported model through the same interface

## Development Workflow

### 1. Initial Planning (Plan Mode)

Start in Plan Mode with a simple prompt that describes your goals. Here's a detailed example:

```
I want to build a React application that allows users to upload PDF files, extract the text content, and translate it between English and Spanish
```

Discuss and refine the approach with Cline by asking clarifying questions until you're satisfied with the plan.

### When to Switch to Act Mode

Based on [Cline's official guidance](https://docs.cline.bot/exploring-clines-tools/plan-and-act-modes-a-guide-to-effective-ai-development), you should switch from Plan Mode to Act Mode when:

1. You have a clear understanding of the solution architecture
2. All major technical decisions have been made:
   - Component structure is defined
   - State management approach is selected
   - File upload handling strategy is determined
   - PDF processing implementation approach is decided
   - Translation system structure is designed
3. Potential challenges and edge cases have been identified
4. You're ready to start writing actual code

The transition should happen at the point where you shift from "what and why" to "how and when" - from design thinking to implementation.

To switch to Act Mode, click "Act".

2. Use the Act/Plan toggle button in the Cline interface (typically found at the bottom of the chat window) to manually switch modes.

3. Select an appropriate model for code generation (recommended: `claude-3.7-sonnet`)

Once in Act Mode, Cline will be ready to help you with the actual implementation of your project, using tools to create files, execute commands, and test your application.

### 2. Project Setup (Act Mode)

Switch to Act Mode and ask Cline to:
1. Set up a new React project with Vite
2. Install necessary dependencies
3. Create the basic project structure

### 3. Implementation (Act Mode)

Continue in Act Mode to implement:
1. PDF upload component
2. Text extraction functionality
3. Translation setup with i18next
4. UI components and styling

### 4. Testing and Refinement (Act Mode)

Use Cline to help:
1. Test the application
2. Debug any issues
3. Refine the user interface
4. Optimize performance

## Project Implementation

### PDF Upload and Text Extraction

We'll use PDF.js to extract text from uploaded PDF files:

1. Handle file uploads using a standard form input
2. Process the uploaded file with PDF.js
3. Extract text content from each page
4. Display the extracted text to the user

### Translation with i18next

We'll implement translation using i18next and react-i18next:

1. Configure i18next with English and Spanish language resources
2. Create translation files for UI elements
3. Use translation hooks for the interface
4. Implement translation of the extracted PDF text

### User Interface

The interface will include:

1. A clean, modern design with responsive layout
2. Drag-and-drop area for PDF uploads
3. Text display area for showing extracted content
4. Language toggle for switching between English and Spanish
5. Clear indication of processing status

## Running the Application

Once the application is ready, follow these steps to run it:

1. Start the development server:
   ```
   npm run dev
   ```

2. Open your browser and navigate to the URL displayed in the terminal (typically http://localhost:5173)