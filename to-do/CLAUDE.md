# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a client-side Korean government office to-do list application built as a single HTML file. The project contains two versions of a task management system:

- **todoend.html**: A feature-rich Korean to-do app ("투두엔드") with glassmorphism design, advanced UI components, comprehensive task management features, and IndexedDB persistence
- **to-do(ChatGPT5).html**: A simpler Korean government office to-do app ("구청 To‑Do") with minimal design and basic task management functionality

Both applications are completely self-contained HTML files with embedded CSS and JavaScript - no build process, dependencies, or server required.

## Development Commands

Since this is a static HTML project with no build system:

**To run the application:**
- Open either HTML file directly in a web browser
- Or serve via any HTTP server: `python -m http.server` or `npx serve`

**To test:**
- Manual testing in browser (no automated test framework)
- Test in multiple browsers for compatibility
- Test responsive design at different screen sizes

**To validate:**
- Use browser DevTools to check for console errors
- Validate HTML with W3C validator
- Test accessibility with browser accessibility tools

## Code Architecture

### Single-File Architecture
Both applications follow a monolithic single-file structure:
- **HTML Structure**: Semantic markup with ARIA labels for accessibility
- **CSS Styles**: Embedded in `<style>` tags with CSS custom properties for theming
- **JavaScript Logic**: Embedded in `<script>` tags with modular organization

### Data Management
- **Storage**: IndexedDB for client-side persistence
- **State Management**: Simple global state object with reactive rendering
- **Data Flow**: State → Render cycle with manual DOM updates

### Key Components

**todoend.html (Advanced Version):**
- **IndexedDB Layer** (lines 321-421): Database operations with error handling
- **App State** (lines 423-436): Global state management with reactive properties
- **Task Operations** (lines 674-799): CRUD operations with validation and error handling
- **UI Components** (lines 610-785): Complex task items with modal editing
- **Event System** (lines 801-950): Comprehensive event handling including keyboard shortcuts

**to-do(ChatGPT5).html (Simple Version):**
- **IndexedDB Layer** (lines 125-206): Basic database operations
- **State Management** (lines 208-221): Minimal state with filtered views
- **Rendering System** (lines 259-356): Simple DOM manipulation
- **Event Handling** (lines 358-420): Basic interaction patterns

### Utility Functions
- **Date Handling**: Korean locale formatting with relative date display
- **Task Filtering**: View-based filtering (today, upcoming, starred, completed) 
- **Search**: Text-based search across task properties
- **Bulk Operations**: Multi-select with batch actions

## Key Features

**Common Features:**
- Korean language interface
- IndexedDB persistence
- Task CRUD operations
- Multiple views (today, upcoming, starred, completed)
- Search functionality
- Keyboard shortcuts
- Responsive design

**todoend.html Advanced Features:**
- Glassmorphism UI design
- Modal editing with form validation
- Advanced task metadata (priority, assignee, tags)
- Comprehensive keyboard shortcuts
- Loading states and error handling
- Notification system
- Bulk operations with visual feedback

## Browser Compatibility

- **IndexedDB**: Modern browsers (IE 10+, Chrome 23+, Firefox 10+, Safari 7+)
- **CSS Grid**: Modern browsers (IE 10+ with prefixes, Chrome 57+, Firefox 52+, Safari 10+)
- **ES6 Features**: Modern browsers (Chrome 51+, Firefox 54+, Safari 10+, Edge 14+)

## Korean Language Considerations

- All UI text is in Korean
- Date formatting uses Korean locale
- Text encoding is UTF-8
- Consider Korean input method editors (IME) for text fields
- Responsive design accommodates Korean text length patterns