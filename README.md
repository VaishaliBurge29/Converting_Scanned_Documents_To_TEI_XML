## Document Processing Pipeline for Historical Documents (TEI XML Output)
This project automates the conversion of scanned historical documents into a structured and searchable TEI XML  format, facilitating analysis and archiving. It leverages the ocrd processor suite for efficient handling of document images and incorporates a flexible approach to accommodate document variations.

### Project Goals
* Structured Output: Generate TEI XML files, an established standard for encoding historical documents.
* Document Versatility: Handle documents with varying characteristics, employing appropriate processing steps based on their specific needs.
* Metadata Extraction: Extract relevant metadata like title, author, date, and page numbers.
  
### System Requirements
* Operating System: Ubuntu or similar Linux distribution (consider WSL for Windows users: https://learn.microsoft.com/en-us/windows/wsl/)
* ocrd_all Package: Provides tools for document image processing and OCR (installation instructions: https://ocr-d.de/en/setup)
- Additional libraries might be required based on the specific configuration.
* Python: Python 3.x (Download from https://www.python.org/downloads/)

### Converting Scanned Documents to TEI XML
For instructions tailored to your needs, you can use the documentation [here](https://github.com/VaishaliBurge29/Converting_Scanned_Documents_To_TEI_XML.git) detailing various processing steps within the OCR-D framework.

### The contents of the files include the following

1. All 24 document folders are uploaded in the `data` folder
2. Each document folder has the processed pages after going through the processing steps by processors.
3. The output folder is located inside the `data` folder, which includes
     - Combined hOCR file 
     - TEI XML conversion python code 
     - TEI XML output file.
4. In the `lib` folder you can find Python code for splitting tiff documents into individual documents and combining hOCR code is also included in the main branch.
5. It also has our Report Document in the `documentation` folder.
