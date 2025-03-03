\# REST API Test Cases - Laravel & PostgreSQL

\## Test Case 1: API Endpoint Availability

\*\*Scenario:\*\* The API should be accessible and respond correctly.

\*\*Given\*\* the API server is running,

\*\*When\*\* a user sends a request to an existing API endpoint,

\*\*Then\*\* the server returns a valid response.

\*\*Remarks:\*\* Ensure all API routes are correctly defined in
\`routes/api.php\`.

\-\--

\## Test Case 2: Database Connection

\*\*Scenario:\*\* The Laravel application should connect to PostgreSQL
without errors.

\*\*Given\*\* the correct database credentials in \`.env\`,

\*\*When\*\* the Laravel application starts,

\*\*Then\*\* it establishes a successful connection to PostgreSQL.

\*\*Remarks:\*\* Check logs for any connection errors.

\-\--

\## Test Case 3: User Registration API

\*\*Scenario:\*\* A user should be able to register via API.

\*\*Given\*\* a user provides valid details (name, email, password),

\*\*When\*\* they send a POST request to \`/api/register\`,

\*\*Then\*\* the system creates a new user.

\*\*Remarks:\*\* Validate that the email is unique and password is
hashed.

\-\--

\## Test Case 4: User Login API

\*\*Scenario:\*\* A registered user logs in.

\*\*Given\*\* a user provides valid login credentials,

\*\*When\*\* they send a POST request to \`/api/login\`,

\*\*Then\*\* the API returns an authentication.

\*\*Remarks:\*\* Validate that incorrect credentials return a \`401
Unauthorized\` error.

\-\--

\## Test Case 5: Fetch User Profile

\*\*Scenario:\*\* A logged-in user fetches their
profile.

\*\*Given\*\* a user is authenticated,

\*\*When\*\* they send a GET request to \`/api/profile\`,

\*\*Then\*\* the API returns user details.

\*\*Remarks:\*\* Unauthorized requests should return a \`401
Unauthorized\` error.

\-\--

\## Test Case 6: Create a Record in PostgreSQL

\*\*Scenario:\*\* Data is saved in the PostgreSQL database.

\*\*Given\*\* a user sends valid data in a POST request,

\*\*When\*\* the request hits the API,

\*\*Then\*\* the data is stored in PostgreSQL successfully.

\*\*Remarks:\*\* Check if the database table updates correctly.

\-\--

\## Test Case 7: Data Validation

\*\*Scenario:\*\* API validates incorrect data before processing.

\*\*Given\*\* a user submits incomplete or invalid data,

\*\*When\*\* they send a request to an endpoint,

\*\*Then\*\* the API returns a error with validation messages.

\*\*Remarks:\*\* Use Laravel's request validation for error handling.

\-\--

\## Test Case 8: Integration with Frontend

\*\*Scenario:\*\* The frontend consumes API responses
correctly.

\*\*Given\*\* the frontend makes a valid API request,

\*\*When\*\* the API responds,

\*\*Then\*\* the frontend correctly displays the data.

\*\*Remarks:\*\* Ensure CORS is enabled for frontend requests.

\-\--

\## Test Case 9: API Error Handling

\*\*Scenario:\*\* The API returns proper error messages.

\*\*Given\*\* an API request encounters an issue,

\*\*When\*\* an error occurs,

\*\*Then\*\* the API returns an error message.

\*\*Remarks:\*\* Standardize error responses with Laravel exception
handling.

\-\--


