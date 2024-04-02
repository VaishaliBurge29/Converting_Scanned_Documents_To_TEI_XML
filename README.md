# Document Processing Pipeline for Historical Documents (TEI XML Output)
This project automates the conversion of scanned historical documents into a structured and searchable TEI XML  format, facilitating analysis and archiving. It leverages the ocrd processor suite for efficient handling of document images and incorporates a flexible approach to accommodate document variations.

##### Project Goals
 * Structured Output: Generate TEI XML files, an established standard for encoding historical documents.
* Document Versatility: Handle documents with varying characteristics, employing appropriate processing steps based on their specific needs.
* Metadata Extraction: Extract relevant metadata like title, author, date, and page numbers.
##### System Requirements
* Operating System: Ubuntu or similar Linux distribution (consider WSL for Windows users: https://learn.microsoft.com/en-us/windows/wsl/)
* Python: Python 3.x (Download from https://www.python.org/downloads/)
* ocrd_all Package: Provides tools for document image processing and OCR (installation instructions: https://ocr-d.de/en/setup)
- Additional libraries might be required based on the specific configuration.

##### Installation (Ubuntu/Linux)
- Install ocrd_all Package:
- Install Python 3.x:
###### Follow the ocrd-d project website instructions for download and installation.

#### Workflow Overview
This pipeline employs a two-tiered approach: initial processing with the ocrd suite and subsequent conversion to TEI XML using a Python script.

##### Tier 1: Preprocessing and OCR with ocrd (if needed)

This section outlines the potential image optimization and layout analysis stages performed by the ocrd suite during document processing. The specific steps employed will depend on the complexity of your historical documents.

**Processors usage:**
All processing occurs within the designated workspace (e.g., 141329).

**Image Optimization (Page Level) and Layout Analysis:**

The ocrd suite offers a variety of processors for image optimization (e.g., binarization, deskewing, dewarping) and layout analysis (e.g., region segmentation). The specific processors and their configuration will depend on the characteristics of your documents.

**For detailed information on available processors, configuration options, and best practices, refer to the ocrd project documentation: https://ocr-d.de/en/use.html**

**Important Considerations:**
- Not all documents require the full range of image optimization and layout analysis options. The selection of processors and their parameters should be tailored to the specific needs of your document collection.
- Consult the ocrd documentation for guidance on choosing appropriate processors and configuring them effectively for your use case

**Splitting Multiple Pages (Optional):**

- If your document is a single pdf containing multiple pages, use a tool like 
 1.`ImageMagick` to split it into individual page images (command not provided, refer to `ImageMagick` documentation) 
2. Command : `convert combined_image.jpg -crop 50%x100% +repage page%d.jpg`
3. Python code file in the repo : `splitting.ipynb`

**Conversion Formats (Optional):**
- XML to HOCR:
Command: `ocrd-fileformat-transform -I OUTPUT -O output1.hocr -P from-to "page hocr"`
- HOCR to TEI:
This conversion is achieved using a separate Python code within this project. Refer to the code documentation for details on its usage and configuration.
**Remember:**
- The specific commands and processing steps employed by the ocrd suite might vary depending on the complexity of your historical documents and the desired output format.
- Consult the ocrd project documentation (https://ocr-d.de/en/setup) for detailed information on available processors, configuration options, and supported output formats.

**Extracted Metadata**
Our code can currently extract the following metadata from the documents:
1. Document Title (if available)
2. Author Information (if available)
3. Date (if available)
4. Page Numbers

**Note:** The ability to extract additional metadata fields can be implemented based on the specific document format and content.
