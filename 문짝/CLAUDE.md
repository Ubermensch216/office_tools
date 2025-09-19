# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**문짝 (Munjjak)** is a client-side document processing tool written as standalone HTML applications. The name means "door" in Korean but also implies "document matching." The tool enables users to merge and split documents (PDF, Excel, ODT, TXT) entirely within their web browser without uploading data to any server.

## Project Structure

This is a **non-traditional codebase** consisting of standalone HTML applications rather than a typical software project:

- **Main applications**: Multiple HTML files (111.html, 222.html, 333.html, etc.) that are iterative versions of the document tool
- **Core application**: `문짝(문서의 짝을 맞추다-문서 병합·분할 도구).html` - The primary single-page application
- **Documentation**: `문짝_사용 설명서.html` - Interactive user manual with infographics
- **Assets**: PNG files for promotional/instructional materials
- **Test files**: `문짝/` directory contains sample documents for testing
- **Backups**: `bak/` directory with previous versions

## Architecture

### Client-Side Processing
- **Zero server dependency**: All processing happens in the browser using JavaScript
- **External libraries via CDN**:
  - `pdf-lib` (v1.17.1) for PDF manipulation
  - `xlsx` (v0.18.5) for Excel file processing
  - `jszip` (v3.10.1) for ZIP/ODT handling
- **File operations**: Drag-and-drop interface with local file processing

### Code Structure
- **Self-contained HTML files**: Each version embeds CSS, JavaScript, and HTML in a single file
- **Global state management**: Uses global variables for file tracking and UI state
- **Event-driven UI**: DOM manipulation with vanilla JavaScript
- **Modular functions**: Separate functions for different file types (PDF, Excel, ODT, TXT)

### Key Functionality Patterns
- **File type detection**: Based on file extension and MIME type
- **Processing pipeline**: File upload → Format selection → Processing → Download
- **ODT handling**: Complex XML parsing and ZIP manipulation for OpenDocument format
- **Error handling**: Try-catch blocks with user-friendly error messages

## Development Workflow

### No Build Process
This project requires **no build tools, package managers, or compilation**. Files are ready to run directly in a web browser.

### Testing
1. Open any HTML file in a modern web browser (Chrome, Firefox, Edge)
2. Test with sample files from the `문짝/` directory
3. Verify merge/split operations work correctly for each supported format

### File Versioning
- Numbered files (111.html, 222.html, 333.html) represent iterative development
- Use descriptive filenames for feature-specific versions (e.g., `moonji_with_odt.html`)
- Keep backup copies in `bak/` directory when making significant changes

## File Processing Capabilities

### Supported Formats
- **PDF**: Merge multiple PDFs, split by page ranges
- **Excel**: Merge sheets, split by sheet or row count
- **ODT**: Merge OpenDocument Text files, split by page ranges
- **TXT**: Merge text files, split by line ranges

### Key Functions
- `processPDFs()`: PDF merge/split using pdf-lib
- `processExcelFiles()`: Excel operations using xlsx library
- `processODTFiles()`: Complex ODT XML manipulation
- `processTxtFiles()`: Text file line-based operations

## UI Components

### Three-Step Workflow
1. **File Selection**: Drag-and-drop zone with file reordering
2. **Operation Selection**: Tabs for merge/split with format-specific options
3. **Execution**: Process files and generate download links

### State Management
- `selectedFiles[]`: Array of uploaded files
- `currentOperation`: 'merge' or 'split'
- Format-specific split types (range, sheet, line, etc.)
- Progress indicators and result display

## Important Notes

- **Security**: No file data leaves the user's browser
- **Performance**: Large files processed entirely in client memory
- **Browser compatibility**: Requires modern browser with ES6+ support
- **File size limits**: Constrained by browser memory limitations