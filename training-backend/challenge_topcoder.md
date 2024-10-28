CHALLENGE OBJECTIVES
In this challenge, we are going to begin the development of the backend REST API for a tool for the Topcoder sales team that they can use during events to showcase previous projects to the potential customers visiting the Topcoder booth.

This challenge will focus on implementing REST API services to support 3 screens:

Home screen
Project list
Project details
You can see the Figma link of the storyboard here: https://www.figma.com/file/rgafvQPyrCOKsHPsbLl03l/TCO22---Sales-Companion-App?node-id=67%3A7225

PROJECT BACKGROUND
Choose from:

Node
MongoDB
Javascript or Typescript (either is acceptable)
Or:

Python
MongoDB
Or

Java 19
MongoDB
SERVICES (MAJOR REQUIREMENT)
The services for these 3 screens in scope are:

Home screen
Project list
Project details
We will need the following REST APIs

GET for a list of all projects, including URL parameters for filtering and sorting.

Filtering by
Category
Industry
Project model
Sorting by
Company size
Timeline
Number of challenges
Number of members involved
Number of individual countries
Number of submissions
Pagination is required.
Per page parameter
Page parameter
In the headers for the response, return these values:
X-Next-Page
X-Page
X-Per-Page
X-Total
X-Total-Pages
GET with an ID parameter to retrieve a single project

POST to add a new project. The POST should return the details of the project added, including the new project ID

PATCH to update an existing project, given JSON for the fields to update and the project ID

DELETE to remove a project, given the project ID

A GET endpoint to search all projects. This can be part of the GET above, or a completely separate endpoint. The search should search all strings in all project fields (title, industry, customer name, descriptions, testimonials, etc...)

POST to save customer contact details

GET to retrieve customer contact details as a list

GET to retrieve a list of testimonials for the home screen. This can be a configurable list of project IDs and the GET just returns the testimonials for those projects in the ID list.

DATA MODEL
A “Project” will contain the fields below.

Unique ID (GUID is fine)
Title of the project
Industry (string) One of:
“Energy, Natural Resources, and Utilities”
“Global Media & Telecom”
“Government & Public Sector”
“Healthcare & Life Sciences”
“Manufacturing & High Tech”
“Retail & Consumer”
Capability (string) One of:
“Apps & Websites”
“Crowdtesting & QA”
“Data Analytics”
“Talent as a Service”
Project model (string) One of:
“Gig”
“Challenge”
“Gig & Challenge”
Customer name
Customer logo (URL to image)
Region (string)
Company size (string, like "10,000 to 50,000")
Project name (string)
Project type (string)
Project short description (string)
Problem long description (string)
Solution (string)
Impact (string)
Timeline (string)
Tracks (array of strings, like "Design, Development, QA")
Number of challenges and tasks run (number)
Number of members involved (number)
Number of individual countries for members involved (number)
Number of submissions (number)
Technology used (string)
Customer testimonials (1 per project)
Text of the customer testimonial
Name of the customer
Photo of the customer
URL to a photo to show
Screenshots of the project (string URL)
For saving a project, all values are required.

For saving customer contact details, all we will save is an email address, and the response should include the generate ID of the record.

Customer email
ID of the record (GUID generated on POST)
RESPONSE CODES
Please ensure that HTTP response codes are used properly and that error and success messages are appropriate and aid in debugging. For instance, if a POST of a new project fails because it’s missing the project title field, the missing field should be explicitly mentioned in the response message.

DATA STORAGE
We will target MongoDB as the data storage for this REST API. Please ensure that the MongoDB connection string is easily configurable in your code.

LANGUAGES
These languages must be used:

Either

Node 16+
Or

Python 3
Or

Java 19
UNIT TESTS
Unit tests are required for this challenge. You must show at least 90% test coverage for your code.

LINT
Your submission must pass lint checks, with the default settings. If you would like a custom setting or rule for some reason, please ask in the forum.

SWAGGER
You must submit a Swagger / OpenAPI YAML document for your REST API that can be used as input into the future integration challenge, ensuring developers know how to use the API.

WHAT TO SUBMIT
Submit the full source code with README for application deployment steps.
Submit a validation document that describes how to validate the individual endpoints and also run the unit tests and see the coverage report.
Submit a Swagger / OpenAPI YAML document
