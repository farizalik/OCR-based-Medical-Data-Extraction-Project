# OCR-based-Medical-Data-Extraction-Project
## Problem Statement
Health insurance companies must follow numerous procedures mandated by government regulations to issue claims. This process requires the insurance companies to handle and analyze images of patient details and prescriptions provided by hospitals or individual doctors to extract useful data. To manage this, most insurance companies outsource this task to companies like "Mr. X Data Analytics," which manually extract information from images.

Mr. X Data Analytics uses software that displays scanned images of patient details or prescriptions. An operator manually types the information from the image into a designated column and selects the type of information. Given that this is a manual process, errors are common, and managing a large volume of images, such as during a pandemic, becomes unfeasible with the same workforce. Additionally, insurance companies require the extracted data to be sent within 24 hours of receipt. These constraints have compelled Mr. X Data Analytics to consider upgrading their existing software

## Solution Approach
We are developing a program that can automatically extract data from images to address these challenges. While machines cannot entirely replace humans, this solution allows a person to review and verify the extracted data before submission. This approach significantly reduces the time and effort required for manual data entry.

We use the Python programming language and the Google Tesseract OCR library (pytesseract) for data extraction. Additionally, the Regex module will be used to process the data and produce the refined, desired output.

## Technologies used
- Python
- oops
- Pdf2image module
- Opencv
- pytesseract
- Regular expression
- pytest
- Postman
- FastApi
## Workflow
![Diagram](https://github.com/farizalik/OCR-based-Medical-Data-Extraction-Project/blob/main/images/workflow.jpg)

## PDF to Image
For converting PDF to image, we have used pdf2image library.

## Without preprocessing extracting data
Tried extracting data from source files without any processing, as they are not in proper format to be extracted, the extracted data was not as expected.
![Diagram](https://github.com/farizalik/OCR-based-Medical-Data-Extraction-Project/blob/main/images/dark_image.jpg)

## Extracted data from the above image
Dr John Smith, M.D
2 Non-Important Street,
New York, Phone (000)-111-2222

Name: Maria Sharapova Date: 5/11/2022

Address: 9 tennis court, new Russia, DC

—momennannenncmneneunnmnnnnninsissiyoinnitnahaadaanih issn earnttneenrenen:

Prednisone 20 mg
Lialda 2.4 gram

3 days,

or 1 month


## Image processing
we decided to preprocess the images using the OpenCV module, before extracting data from them. For that, we have first used normal thresholding and checked, which resulted in below image


![Diagram](https://github.com/farizalik/OCR-based-Medical-Data-Extraction-Project/blob/main/images/filter_dark.jpg)

So, if there is any shadow or some noise, the normal thresholding fades out the area. which will result in a loss of data.
In the search for a better approach to this problem, we have decided to use the adaptive thresholding technique. In this technique, the image will be divided into sub-images and the thresholding value will be different for all sub-regions. The end result of adaptive thresholding is much better compared to normal thresholding.

![Diagram](https://github.com/farizalik/OCR-based-Medical-Data-Extraction-Project/blob/main/images/adaptive_filter_dark.jpg)

## After preprocessing the image data extraction

Dr John Smith, M.D
2 Non-Important Street,
New York, Phone (000)-111-2222

Name: Marta Sharapova Date: 5/11/2022

Address: 9 tennis court, new Russia, DC

K

Prednisone 20 mg
Lialda 2.4 gram

Directions:

Prednisone, Taper 5 mg every 3 days,
Finish in 2.5 weeks a
Lialda - take 2 pill everyday for 1 month

## Notebook
For all these above trials, used jupyter books and developed the small bits of the functionalities., which can be used later while designing the class.
[notebooks](https://github.com/farizalik/OCR-based-Medical-Data-Extraction-Project/tree/main/backend/notebooks)

## OOPS design
The code was written in using OOPs concepts for extracting the medical data from prescription and patient details documents.
[codes](https://github.com/farizalik/OCR-based-Medical-Data-Extraction-Project/tree/main/backend/src )

## Regular expression
using regular expression module we can match the patterns and extract the data we want from the files. For this project, analyst the medical files and as fact all the medical documents will follow same pattern, we wrote patterns that match only the required data. Before writing the python code, It is advisable to practise and match the patterns in regex 101 website.
[regex101.com](https://regex101.com/)

## Test driven Development
In this project test driven development methodology was used to develop the code. For testing pytest module was used. For all the methods and final result the test cases was designed and checked simultaneously while developing the code.



