# OCR-img-to-txt-search

## Project Overview: Image Text Extraction and Student Image Sorting

This project automates the process of extracting student IDs from images using Optical Character Recognition (OCR) and organizing them into designated folders based on the IDs found. It is designed to streamline the management of student-related image files, particularly in academic or administrative settings.

### Key Features
1. **OCR Text Extraction:**  
   Uses `pytesseract` to extract textual content from image files in various formats (e.g., `.tif`, `.png`). Supports both Arabic and English text recognition.

2. **Automated Image Sorting:**  
   - Searches for specific student IDs within the extracted text from each image.
   - Moves images containing a specific student ID to a dedicated folder named after that student ID.

3. **Dynamic Folder Management:**  
   - Automatically creates a folder for each student ID if it does not already exist.
   - Ensures images are added to existing folders without overwriting or creating duplicates.

4. **Efficiency:**  
   Stops further processing for a student ID once at least one matching image is found, optimizing runtime for large datasets.

5. **Error Handling:**  
   Catches and logs exceptions to ensure smooth execution even when errors (e.g., corrupted images) occur.

---

### Workflow Summary
1. **Input Directory Setup:**  
   Place the images to be processed in a source folder.

2. **Specify Student IDs:**  
   Provide a list of student IDs to search for in the images.

3. **Run the Script:**  
   - The script iterates through all images in the source folder.
   - Text is extracted from each image using Tesseract OCR.
   - For each student ID found, the corresponding image is moved to a target folder within a subdirectory named `student_<StudentID>`.

4. **Output Organization:**  
   - Each student’s images are stored in their respective folders within the target directory.
   - If a folder already exists and contains files, new images are simply added to it without affecting the existing contents.

---

### Example
#### Input:
- Source folder: `/content/drive/MyDrive/NMU/analyses/imgsearch/Done_aie111-11212024093918/cse261-New1111`
- Target folder: `/content/drive/MyDrive/imgsearch/ms12_folder2/CSE261`
- Student IDs: `["222101512"]`

#### Output:
- `/content/drive/MyDrive/imgsearch/ms12_folder2/CSE261/student_222101512/`  
  Contains all images with the ID `222101512`.

---

### Prerequisites
- Python environment with the following libraries:
  - `Pillow`
  - `pytesseract`
  - `shutil`
  - `os`
- Tesseract OCR installed and configured on your system.

### How to Run
1. Clone the repository.
2. Update the source folder, target folder, and student IDs in the script.
3. Run it   
4. Check the target folder for the organized output.

### Potential Use Cases
- Automating student image processing for exams or administrative records.
- Extracting and categorizing scanned documents or forms based on specific identifiers.

This project can easily be extended to support additional formats, identifiers, or workflows as needed.
