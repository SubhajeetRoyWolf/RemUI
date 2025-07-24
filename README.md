Test Plan and Documentation
1. Objective
Automate UI and API testing for a simple web application. The goal is to validate user flows like login, item management, and order placement.
________________________________________
2. Application Overview
•	Frontend: Dummy E-commerce Website (React.js based) GitHub Repo
•	Backend: Hotel Booking API (Node.js + Express)
•	Features: User login, order placement (UI); item and booking management (API)
________________________________________
3. Test Plan
3.1 What is Being Tested
•	User Login (UI and API)
•	Order Placement (UI)
•	Hotel Booking Management (API)
o	Create, Retrieve, Update, Delete bookings
*API testing was designed and implemented using the official task guidelines provided in the assignment email, which outlined required endpoints such as `**, ****\`** along with both positive and negative test cases. This ensured alignment with the expected evaluation criteria.*
3.2 Test Coverage Areas
UI (Using Selenium)
•	✅ Login with valid credentials
•	✅ Login with invalid credentials
•	✅ Place a new order (UI flow)
•	✅ Validate order confirmation or error message
API (Using Postman/Newman)
•	✅ POST /login – with valid/invalid credentials
•	✅ GET /hotels – validate response schema and data
•	✅ POST /booking – create new booking (positive/negative)
•	✅ PUT /booking/:id – update booking
•	✅ DELETE /booking/:id – delete booking
3.3 Tools Used and Why
Tool	Purpose
Selenium	UI Functional Automation
Postman	API testing and automation
Newman	CLI automation for Postman
Jenkins	CI Integration
________________________________________
4. How to Run the Tests
UI Tests – Setup & Execution
Prerequisites
•	Python installed
•	Firefox and/or Chrome browser installed
•	ChromeDriver available in system PATH
•	Virtual environment created with pytest and selenium installed manually
Steps
1.	Clone the UI testing repository:
 	git clone https://github.com/SubhajeetRoyWolf/RemUI.git
cd RemUI
2.	Create and activate virtual environment:
 	python -m venv .venv
.venv\Scripts\activate     # On Windows
3.	Install required packages:
 	pip install selenium pytest
4.	Run UI tests:
 	pytest --browser_name=firefox
5.	To generate an HTML report:
 	pytest --html=reports\report.html
✅ Run via Jenkins (Generic Command)
cd C:\Path\To\Your\Project\pythonpackage
call ..\.venv\Scripts\activate.bat
python -m pytest --browser_name=firefox --html="../reports/report.html"
________________________________________
API Tests
1.	Clone API test repo:
 	git clone https://github.com/SubhajeetRoyWolf/REM-API-test.git
cd REM-API-test/postman
2.	Ensure you have Newman installed globally:
 	npm install -g newman
3.	Run Newman CLI:
 	newman run SampleTest.postman_collection.json --reporters cli,html --reporter-html-export reports/report.html
✅ Run API Tests via Jenkins (Generic Path)
cd path\to\REM-API-test\postman
newman run SampleTest.postman_collection.json --reporters cli,html --reporter-html-export reports\report.html
________________________________________
5. Assumptions / Limitations
•	UI tests are validated against known static elements (not dynamic DOM)
•	Login requires hardcoded valid credentials (can be parameterized)
•	No mock server used — all tests run against the actual backend
•	Order placement tested with simplified schema (no payment gateway)
________________________________________
6. README (Quick Setup)
Prerequisites
•	Node.js (for backend)
•	Python + pip (for UI tests)
•	ChromeDriver in PATH
•	Newman installed globally: npm install -g newman
Steps
# Clone API repo
https://github.com/SubhajeetRoyWolf/REM-API-test.git
cd REM-API-test/postman

# Run API tests
newman run SampleTest.postman_collection.json --reporters cli,html --reporter-html-export reports/report.html

# Clone UI repo
https://github.com/SubhajeetRoyWolf/RemUI.git
cd RemUI

# Run UI tests
python -m venv .venv
.venv\Scripts\activate
pip install selenium pytest
pytest --browser_name=firefox
________________________________________
✅ Ready for Submission You can submit this test setup via the form link provided in the job description.
