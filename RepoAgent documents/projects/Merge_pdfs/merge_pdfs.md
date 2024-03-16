## FunctionDef by_appending
**by_appending**: The function of by_appending is to merge PDF files by appending them one after the other.

**parameters**: 
· No parameters are required for this function.

**Code Description**: 
The function starts by creating a PdfFileMerger object called `merger`. It then appends the contents of two PDF files to the `merger` object. The first PDF file, "samplePdf1.pdf", is opened as a file stream (`f1`) and appended to the `merger`. The second PDF file, "samplePdf2.pdf", is directly appended to the `merger`. Finally, the merged PDF file is written to a new file named "mergedPdf.pdf".

**Note**: 
- Ensure that the PDF files "samplePdf1.pdf" and "samplePdf2.pdf" exist in the specified paths before running the function.
- The merged PDF file will be created as "mergedPdf.pdf" in the same directory where the script is executed.
## FunctionDef by_inserting
**by_inserting**: The function of by_inserting is to merge PDF files by inserting one PDF into another at a specified position.

**parameters**:
- No parameters are required for this function.

**Code Description**:
The function initializes a PdfFileMerger object called `merger`. It then appends the content of "samplePdf1.pdf" to the `merger` object. Next, it merges "samplePdf2.pdf" into the `merger` object at position 0. Finally, it writes the merged content into a new PDF file named "mergedPdf1.pdf".

**Note**:
- Ensure that the paths to the PDF files are correct and accessible from the location where the script is executed.
- The position parameter in the `merge` method starts from 0 for the first page.
