# GEMINI Project Context: 문짝 (Munjjak) - Document Tool

## Directory Overview

This directory contains **문짝 (Munjjak)**, a client-side web tool designed for merging and splitting documents. The name is a Korean wordplay, meaning "door" but also implying "document matching."

The core of the project is a standalone HTML application that runs entirely in the user's web browser. It uses JavaScript libraries to process files locally, ensuring that no user data is ever uploaded to a server. This makes the tool fast, secure, and usable offline.

The directory holds the main web application, a comprehensive user manual, related image assets, and a folder with example documents.

**Project Type:** Non-Code Project (from a development standpoint, as it's a serverless, single-file web application).

## Key Files

*   `문짝(문서의 짝을 맞추다-문서 병합·분할 도구).html`: This is the main application. It's a single-page web app that provides the entire user interface and functionality for merging and splitting files.
*   `문짝_사용 설명서.html`: A detailed, infographic-style user guide. It explains the tool's purpose, features, and the 3-step workflow.
*   `문짝/` (directory): Contains various sample documents in PDF, ODT, and XLSX formats. These appear to be test cases or examples for the tool.
*   `문짝_인포그래픽 포스터.png` & `문짝_프로그램_캡쳐.png`: Promotional or explanatory visual assets for the tool.
*   `bak/`: A backup directory containing a previous version of the main HTML file.

## Usage

The tool is designed for simplicity and security.

1.  **To Run:** Open the `문짝(문서의 짝을 맞추다-문서 병합·분할 도구).html` file in a modern web browser (like Chrome, Edge, or Firefox).
2.  **Workflow:**
    *   **Step 1: File Selection:** Drag and drop the files you want to process (PDF, XLSX, or TXT) into the designated area. You can reorder the files by dragging them.
    *   **Step 2: Operation Selection:** Choose either the "Merge" or "Split" tab.
        *   **Merge:** Combine multiple files of the same type into one.
        *   **Split:** Divide a single file based on specific criteria (e.g., page ranges for PDFs, row counts for Excel, or line numbers for TXT).
    *   **Step 3: Execute & Download:** Click the "실행하기" (Execute) button. The processing happens instantly in your browser, and download links for the resulting files will appear.
