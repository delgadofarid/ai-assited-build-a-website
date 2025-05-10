# PDF Text Extraction and Translation Website

A React-based application that allows users to upload PDF files, extract text content, and translate it from English to Spanish using i18next.

## Project Overview

This project demonstrates the capabilities of AI-assisted development using Cline to build a functional website with the following features:
- PDF file upload functionality
- Text extraction from the uploaded PDF
- Translation of the extracted text between English and Spanish

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

## Interface de Cline

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

### `.clinerules/` Folder

According to the [Cline documentation on prompting](https://docs.cline.bot/improving-your-prompting-skills/prompting), effective `.clinerules` files should provide clear context and goals. Following these guidelines, create a `.clinerules` folder in your project root with content like:

```
ai-assisted-build-a-website/
└── .clinerules/
    ├── 00-role.md       # Cline Agent - role
```

00-role.md
```
You are an experienced Javascript / React developer with expertise in building web applications with file upload capabilities and PDF processing.

If provided with a GitHub URL, use the github MCP server to fetch the content.
```

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
Create a user-friendly react web site for uploading PDF files that extract text content from uploaded PDFs and displays it in the UI
```

Discuss and refine the approach with Cline by asking clarifying questions until you're satisfied with the plan.

### When to Switch to Act Mode

Based on [Cline's official guidance](https://docs.cline.bot/exploring-clines-tools/plan-and-act-modes-a-guide-to-effective-ai-development), you should switch from Plan Mode to Act Mode when:

1. You have a clear understanding of the solution architecture
2. All major technical decisions have been made
3. Potential challenges and edge cases have been identified
4. You're ready to start writing actual code

The transition should happen at the point where you shift from "what and why" to "how and when" - from design thinking to implementation.

To switch to Act Mode, click "Act".

2. Use the Act/Plan toggle button in the Cline interface (typically found at the bottom of the chat window) to manually switch modes.

3. Select an appropriate model for code generation (recommended: `claude-3.7-sonnet`)

Once in Act Mode, Cline will be ready to help you with the actual implementation of your project, using tools to create files, execute commands, and test your application.

> Be careful of not auto-approving actions that can give the agent too much freedom to be harmful.

### 2. Project Setup (Act Mode)

Switch to Act Mode and ask Cline to:
1. Set up a new React project with Vite
2. Install necessary dependencies
3. Create the basic project structure

### 3. Implementation (Act Mode)

Continue in Act Mode to implement:
1. PDF upload component
2. Text extraction functionality
3. Translation setup with a simple node library

### 4. Testing and Refinement (Act Mode)

Use Cline to help:
1. Debug any issues: Ask Cline to test the application on a browser to identify and recover from errors

## Running the Application

Once the application is ready, follow these steps to run it:

1. Start the development server:
   ```
   cd [app_folder] && npm run dev
   ```

2. Open your browser and navigate to the URL displayed in the terminal (typically http://localhost:5173)