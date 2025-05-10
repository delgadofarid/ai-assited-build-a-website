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
