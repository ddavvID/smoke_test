# What is Smoke Testing?

Smoke Testing is a <span style="color:blue">software testing process</span> used to determine whether a newly deployed software build is stable enough for further testing. It acts as a preliminary check for the QA team to decide whether to proceed with more in-depth testing. This type of testing involves running a minimal set of tests on each build to verify basic functionalities. Smoke Testing is also referred to as “<span style="color:green">Build Verification Testing</span>” or “<span style="color:green">Confidence Testing</span>.”

In simpler terms, smoke testing ensures that the critical features of the software are functioning correctly and that there are no major issues (showstoppers) in the build being tested. It serves as a quick and focused regression test of the core functionality, providing confidence that the product is ready for more comprehensive testing. By identifying significant flaws early, smoke testing helps avoid wasting time and resources on testing a build that is fundamentally broken.

## When Do We Perform Smoke Testing?

<span style="color:red">Smoke Testing</span> is conducted whenever new functionalities are developed and integrated into the existing build that is deployed in the QA or staging environment. Its primary purpose is to verify whether all critical functionalities are working as expected.

## How Smoke Testing Works

In this testing method, the development team deploys the build to the QA environment. The QA team then selects a subset of test cases and executes them on the build. These test cases focus on critical functionalities to identify any major issues in the build. If the tests pass, the QA team proceeds with more detailed functional testing. However, if any test fails, the build is returned to the development team for fixes. Smoke Testing is repeated whenever there are changes to the build to ensure its stability.

**Example:**
If a new "<span style="color:purple">Registration</span>" button is added to the login window and the build is deployed with this new code, smoke testing is performed to verify that the button works as intended and does not break the existing functionality.

## Purpose of Smoke Testing

Smoke Testing qualifies the build for further formal testing. Its main goal is to detect major issues early in the development cycle. These tests are designed to demonstrate system stability and ensure that the build meets the basic requirements. A build includes all necessary components, such as data files, libraries, reusable modules, and engineered components, required to implement one or more product functionalities.

## What Happens If We Skip Smoke Testing?

If smoke testing is not performed in the early stages, defects may go unnoticed and surface in later stages of testing or even in production. These defects can become showstoppers, significantly delaying the release of deliverables and increasing the cost of fixing issues. Early detection through smoke testing helps prevent such scenarios and ensures a smoother development and release process.

## Why Do We Perform Smoke Testing?

Smoke Testing is a critical step in the software development process as it ensures the stability and correctness of the system in its early stages. By conducting smoke testing, we can save significant testing effort and resources. It helps bring the system to a stable state, allowing the QA team to proceed with more detailed functional testing only after the build passes the smoke test.

### Key Reasons for Performing Smoke Testing:

- **Identify Showstoppers Early:** Smoke testing helps detect major issues (showstoppers) in the build that could block further testing or development.
- **Early Defect Detection:** It is performed after the build is released to the QA environment, enabling the identification of most defects in the initial stages of software development.
- **Simplify Defect Resolution:** Smoke testing simplifies the process of detecting and correcting major defects, reducing the time and effort required for debugging later.
- **Validate New Code:** It helps the QA team identify defects in the application functionality that may have been introduced by new code or changes.
- **Focus on Critical Issues:** Smoke testing targets major severity defects, ensuring that the core functionalities of the system are working as expected before moving forward.

## How to Perform Smoke Testing?

Smoke Testing is typically performed manually, though it can also be automated depending on the organization's processes and requirements. The approach may vary from one organization to another.

### Manual Smoke Testing

In most cases, smoke testing is done manually. The process involves verifying that the critical paths and functionalities of the application are working as expected without any major issues. Here’s how it works:

1. **Build Deployment:** After the build is released to the QA environment, the QA team selects high-priority test cases that cover the most critical functionalities.
2. **Test Execution:** The selected test cases are executed to identify any critical defects in the system.
3. **Evaluation:**
   - If the tests pass, the QA team proceeds with further functional testing.
   - If the tests fail, the build is rejected and sent back to the development team for fixes.
   - Once a new build version is released, smoke testing is repeated to ensure stability.
4. **Integration Check:** Smoke testing is also performed on new builds to ensure they integrate correctly with existing functionalities.
5. **Build Verification:** Before starting smoke testing, the QA team must verify that the correct build version is being tested.

### Automated Smoke Testing

While automation is commonly used for regression testing, it can also be applied to smoke testing. Automated smoke testing involves running a predefined set of test cases against the build to verify its stability. Here’s how it works:

1. **Test Case Recording:** Test engineers record the manual steps performed during smoke testing using an automation tool.
2. **Build Verification:** Whenever a new build is ready for deployment, the recorded automated test cases are executed to check if the major functionalities are working properly.
3. **Immediate Feedback:**
   - If the automated tests pass, the build is considered stable and ready for further testing.
   - If the tests fail, the development team can quickly address the issues and redeploy the build.
4. **Time and Effort Savings:** Automation eliminates the need for repetitive manual testing, saving time and ensuring a faster turnaround for delivering a stable build to the QA environment.

### Choosing Between Manual and Automated Smoke Testing

- **Manual Smoke Testing:** Suitable for smaller projects or when the test cases are not repetitive.
- **Automated Smoke Testing:** Ideal for larger projects or when frequent builds are deployed, as it saves time and ensures consistency.

## Advantages of Smoke Testing

Smoke Testing offers several benefits that contribute to the efficiency and quality of the software development process. Here are the key advantages:

- **Easy to Perform:** Smoke testing is straightforward and can be executed quickly, making it accessible for both manual and automated approaches.
- **Early Defect Detection:** It helps identify critical defects in the early stages of development, preventing issues from escalating into more complex problems later.
- **Improved System Quality:** By verifying the stability of the build, smoke testing ensures that the system meets basic functionality requirements, enhancing overall quality.
- **Reduced Risk:** It minimizes the risk of deploying a flawed build, ensuring that major issues are caught before further testing or release.
- **Progress Tracking:** Smoke testing provides a clear indication of the build's stability, making it easier to assess progress and determine if the software is ready for the next phase of testing.
- **Saves Time and Effort:** By catching major issues early, smoke testing reduces the need for extensive debugging later, saving both time and effort in the testing process.
- **Quick Error Detection and Correction:** Critical errors are identified and corrected early, ensuring a smoother development process and reducing delays.
- **Fast Execution:** Smoke tests are designed to run quickly, providing immediate feedback on the build's stability.
- **Minimized Integration Risks:** It ensures that new changes or features integrate seamlessly with the existing system, reducing the risk of integration-related issues.

## Sample Smoke Test Cases Example

Below is an example of smoke test cases for a web application, including test scenarios, steps, expected results, actual results, and status:

| T.ID | TEST SCENARIOS                | DESCRIPTION                                                         | TEST STEPS                                                                                          | EXPECTED RESULT                       | ACTUAL RESULT                        | STATUS |
|------|-------------------------------|---------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------|--------------------------------------|--------|
| 1    | Valid login credentials       | Test the login functionality to ensure a registered user can log in successfully. | 1. Launch the application <br> 2. Navigate to the login page <br> 3. Enter valid username <br> 4. Enter valid password <br> 5. Click the login button | Login should be successful           | Login is successful                  | Pass   |
| 2    | Adding item functionality     | Verify that an item can be added to the cart.                       | 1. Select from the categories list <br> 2. Add the item to the cart                                 | Item should be added to the cart      | Item is not added to the cart        | Fail   |
| 3    | Sign out functionality        | Check if the user can sign out successfully.                        | 1. Click the sign-out button                                                                        | User should be signed out             | User is not able to sign out         | Fail   |

### Explanation of the Test Cases

**Valid Login Credentials:**
- **Purpose:** To verify that registered users can log in successfully using valid credentials.
- **Result:** The test passes if the login is successful.

**Adding Item Functionality:**
- **Purpose:** To ensure that users can add items to their cart.
- **Result:** The test fails because the item is not being added to the cart, indicating a potential issue with the cart functionality.

**Sign Out Functionality:**
- **Purpose:** To confirm that users can sign out of the application.
- **Result:** The test fails because the
