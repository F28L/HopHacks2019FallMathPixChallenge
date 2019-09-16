# HopHacks2019FallMathPixChallenge
## Collaborators: Sandeep Ramesh, Sean O'Connor, Jeffery Zhou, Nehali Gupta

## Inspiration
Having been interested after hearing about Mathpix in the past, we decided that it would be a good idea to take this opportunity to both potentially improve this product and further our own understanding of coding.

## What it does
Our program takes the inputted document (normally a PDF but a small modification allows it to be either JPG or PNG) and breaks it along horizontal blank lines. The blank lines are found by detecting when the average grayscale value of a row is greater than or equal to the median of the average grayscale value of all the rows. This is a rough but workable solution. We will aim to improve this comparison in the future.

Following this, the image is then split into different horizontal blocks; each run of non-blank lines, along with the two runs of blank lines adjacent to it, form a horizontal slice of the original image. The relevant cropping data is then sent to the Mathpix OCR API, along with the encoded image data, which returns Mathpix's interpretation of each individual block of text from the image. This is then printed out along with a new line character at the end, to ease copying of the LaTeX representation into another document. This works surprisingly well in converting PDFs, such as math papers, into both text and LaTeX. 

## How I built it
This program was coded in Python, using the Mathpix OCR API as well as several modules. Namely, pdf2image was used to convert the inputted PDF into a JPG format, which was necessary, as both the Mathpix API and the parsing program required either JPG or PNG. Helping each other bug-test and put together the overall program, we successfully implemented our original idea, with a few improvements, and were able to parse a full-sized PDF document into LaTeX.

## Challenges I ran into
We ran into several challenges with regards to programming, both in the case of creating an algorithm that worked and interacting with the API to obtain the results we needed. This included making sure the blank-line-recognition algorithm worked successfully in most cases and interacting with the API in a way that allowed us to obtain the information we needed.
We also attempted to further analyze the page vertically to detect and remove margins, however, we were unable to integrate this into the code properly or effectively.

## Accomplishments that I'm proud of
We're proud of working together as a team and managing to implement our original idea for this project. Furthermore, we're extremely happy with how well our image slicing algorithm worked, especially since the main idea was only slightly changed throughout the course of the project.

## What I learned
We learned how to collaboratively work together on a coding project as well as using several libraries and APIs together with each other.
Sandeep- I personally never used Python prior to this project so spending a couple hours at the beginning watching tutorials and learning Python was one of my biggest takeaways from this challenge.

## What's next for Mathpix PDF/Image Parser
Our program could be improved in several ways, namely the detection of lines of text and the cropping of the image into readable blocks, but the fundamental idea of breaking up a document horizontally to allow the Mathpix API to interpret each line of text or math equations should be sound. As mentioned early, adding a vertical analysis of the document to overlay the horizontal analysis could help make the code more efficient. 
