Devloped a online job search application "Jobby App" using React.js

### Refer to videos below:

<div style="text-align: center;">
  <video style="max-width:80%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12);outline:none;" loop="true" autoplay="autoplay" controls="controls" muted>
    <source src="https://assets.ccbp.in/frontend/content/react-js/jobby-app-success-output-v0.mp4" type="video/mp4">
  </video>
</div>
<br/>


### Design Files


- Login Route
- Home Route
- Jobs Route
- Job Item Details Route
- Not Found Route
- Protected Route
- Fiters

### Set Up Instructions

<details>
<summary>Click to view</summary>

- Download dependencies by running `npm install`
- Start up the app using `npm start`
</details>

### Completion Instructions

<details>
<summary>Functionality to be added</summary>
<br/>

The app must have the following functionalities

- **Login Route**

  - When invalid credentials are provided and the **Login** button is clicked, then the error message received from the response.
  - When valid credentials are provided and the **Login** button is clicked, then the page is navigated to the Home Route
  - When an _unauthenticated_ user, tries to access the Home, Jobs and Job Item Details Route, then the page is navigated to Login Route
  - When an _authenticated_ user, tries to access the Home, Jobs and Job Item Details Route, then the page will navigated to the respective route
  - When an _authenticated_ user, tries to access the Login Route, then the page is navigated to the Home Route

- **Home Route**

  - When an _authenticated_ user opens the Home Route
    - Clicks on the **Find Jobs** button, then the page is to the Jobs Route

- **Jobs Route**

  - When an _authenticated_ user opens the Jobs Route

    - An HTTP GET request should be made to **Profile API URL**
      - **_loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received.
      - If the HTTP GET request made is unsuccessful, then the [Failure View](https://assets.ccbp.in/frontend/content/react-js/jobby-app-profile-failure-lg-output.png) is displayed.
        - When the **Retry** button is clicked, an HTTP GET request should be made to **Profile API URL**
    - An HTTP GET request should be made to **Jobs API URL** with `employment_type`, `minimum_package`, `loction` and `search` as query parameters with empty strings as initial values
      - **_loader_** should be displayed while fetching the data
      - After the data is fetched successfully, display the list of jobs received from the response
      - If the HTTP GET request made is unsuccessful, then the [Failure View](https://assets.ccbp.in/frontend/content/react-js/jobby-app-jobs-failure-lg-output.png) is displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to **Jobs API URL**
    - When a value is provided in the search input and search icon button is clicked
      - Make an HTTP GET request to the **Jobs API URL** with `jwt_token` in the Cookies and query parameter `search` with value as the text provided in the search input
      - **_loader_** will fetching the data.
      - After the data is fetched successfully, display the list of jobs received from the response
    - When **Employment Types** options are selected
      - Make an HTTP GET request to the **Jobs API URL** with `jwt_token` in the Cookies and query parameter `employment_type` with value as a list of selected employment type id's as a single string separated by `,`
      - **_loader_** should be displayed while fetching the data
      - After the data is fetched successfully, display the list of jobs received from the response
    - When **Salary Range** is selected
      - Make an HTTP GET request to the **Jobs API URL** with `jwt_token` in the Cookies and query parameter `minimum_package` with value as the id of the selected salary range
      - **_loader_** should be displayed while fetching the data
      - After the data is fetched successfully, display the list of jobs received from the response
    - When the HTTP GET request made to the **Jobs API URL** returns an empty list for jobs then [No Jobs View](https://assets.ccbp.in/frontend/content/react-js/jobby-app-no-jobs-lg-output.png) will be displayed

  - When multiple filters are applied, then the HTTP GET request should be made with all the filters that are applied
  - For example: When the **Full Time** and **Part Time** employment types are selected, salary range **10 LPA and above** is selected and search input field is empty, then the **Jobs API URL** will be as follows

    ```js
    const apiUrl = 'https://apis.ccbp.in/jobs?employment_type=FULLTIME,PARTTIME&minimum_package=1000000&search='
    ```

  - When a **job** is clicked, then the page should be navigated to the Job Item Details Route

- **Job Item Details Route**

  - When an _authenticated_ user opens the Job Item Details Route
    - An HTTP GET request should be made to **Job Details API URL** with `jwt_token` in the Cookies and job `id` as path parameter
      - **_loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received should be displayed
      - The list of similar jobs should be displayed
      - If the HTTP GET request made is unsuccessful, then the [Failure View](https://assets.ccbp.in/frontend/content/react-js/jobby-app-job-details-failure-lg-output.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to **Job Details API URL**
  - When the **Visit** button is clicked, then the corresponding company website URL should be opened in a new tab

- **Not Found Route**

  - When a random path is provided as the URL path, then the page should be navigated to the Not Found Route

- **Header**

  - When the **website logo** image is clicked, then the page should be navigated to the Home Route
  - When the **Home** link is clicked, then the page should be navigated to the Home Route
  - When the **Jobs** link is clicked, then the page should be navigated to the Jobs Route
  - When the **Logout** button is clicked, then the page should be navigated to the Login Route

- The App is provided with `employmentTypesList`. It consists of a list of employment type objects with the following properties in each employment type object

  |       Key        | Data Type |
  | :--------------: | :-------: |
  | employmentTypeId |  String   |
  |      label       |  String   |

- The App is provided with `salaryRangesList`. It consists of a list of salary range objects with the following properties in each salary range object

  |      Key      | Data Type |
  | :-----------: | :-------: |
  | salaryRangeId |  String   |
  |     label     |  String   |

  - The App is provided with `locationsList`. It consists of a list of location objects with the following properties in each location object

  |      Key      | Data Type |
  | :-----------: | :-------: |
  | locationId    |  String   |
  |     label     |  String   |

</details>

<details>

<summary>user crediential</summary>

<br/> 
   
   username: rahul
   password: rahul@2021


