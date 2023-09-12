

# Fabric Supply Chain API Documentation

This documentation outlines the various routes and functionalities provided by the Fabric Supply Chain application.

## Admin Routes

### Admin Login [/adminLogin]

- **Method**: POST
- **Description**: Admin login through their credentials, granting access to perform administrative operations.
- **Usage**: To access admin functionalities.
- **Request Body**:
  - `username` (string): Admin username
  - `password` (string): Admin password
- **Response**: JWT token for authentication.

### Admin Delete User [/adminDelete]

- **Method**: DELETE
- **Description**: Allows the admin to delete any user.
- **Usage**: To delete a user account.
- **Request Body**:
  - `userId` (string): ID of the user to be deleted.
- **Authorization**: JWT token with admin privileges.

### Get All Users [/admin]

- **Method**: GET
- **Description**: Provides the admin access to view details of all users.
- **Usage**: To retrieve a list of all user profiles.
- **Authorization**: JWT token with admin privileges.

### Admin File Upload [/adminFile]

- **Method**: POST
- **Description**: Allows the admin to store a file in the database for the organization.
- **Usage**: To upload a file for organizational use.
- **Request Body**: File upload.

## File Routes

### Generate Certificate Security Key [/zip]

- **Method**: GET
- **Description**: Generates a certificate security key and allows downloading as a zip file to the local machine.
- **Usage**: To generate and download a security key.
- **Response**: ZIP file containing security key and certificates.

### Get Security Key and Certificates [/zip]

- **Method**: GET
- **Description**: Retrieves the security key and certificates from the database.
- **Usage**: To get security-related information.
- **Response**: Security key and certificates data.

## User Registration Routes

### User Registration [/register]

- **Method**: POST
- **Description**: Allows users to register and sends a verification email.
- **Usage**: To create a new user account.
- **Request Body**:
  - `username` (string): User's chosen username
  - `email` (string): User's email address
  - `password` (string): User's chosen password
- **Response**: Success message and verification email sent.

### Email Verification [/verified]

- **Method**: GET
- **Description**: Verifies user email after checking JWT token validity.
- **Usage**: To verify user email.
- **Authorization**: JWT token required for verification.

## User Login Routes

### User Login [/login]

- **Method**: POST
- **Description**: Allows users to log in with two-factor authentication (2FA).
- **Usage**: To log in to the user account.
- **Request Body**:
  - `username` (string): User's username
  - `password` (string): User's password
- **Response**: Sends an OTP to the registered email for 2FA.

### Verify OTP [/verifyOTP]

- **Method**: POST
- **Description**: Verifies the OTP sent to the user's email address.
- **Usage**: To complete the 2FA login process.
- **Request Body**:
  - `otp` (string): OTP received by email
- **Response**: JWT token for successful login.

### Resend OTP [/resendOTP]

- **Method**: POST
- **Description**: Resends OTP to the user's email address if it expires.
- **Usage**: To request a new OTP for 2FA.
- **Response**: Success message and OTP resent.

### Delete User Account [/delete]

- **Method**: DELETE
- **Description**: Allows users to delete or deactivate their account with proper authentication.
- **Usage**: To delete the user account.
- **Authorization**: JWT token required for deletion.

## Password Reset and Update Routes

### Send Reset Password Link [/resetpasswordLink]

- **Method**: POST
- **Description**: Allows users to request a reset password link with a token sent to their registered email.
- **Usage**: To initiate the password reset process.
- **Request Body**:
  - `email` (string): User's registered email
- **Response**: Success message and reset link sent.

### Reset Password [/resetpassword]

- **Method**: POST
- **Description**: Allows users to reset their password using the token from the reset link.
- **Usage**: To reset the user's password.
- **Request Body**:
  - `token` (string): Token from the reset link
  - `newPassword` (string): User's new password
- **Response**: Success message and password reset.

### Update Password [/updatePassword]

- **Method**: POST
- **Description**: Allows users to update their password after logging in.
- **Usage**: To change the user's password.
- **Request Body**:
  - `oldPassword` (string): User's current password
  - `newPassword` (string): User's new password
- **Authorization**: JWT token required for updating the password.

## Flow Chart of Fabric Supply Chain

![Flow Chart](https://github.com/devstacktanya/FabricSupplyFlowchart/blob/main/Fabric%20Supply%20chain.drawio.png)



This documentation outlines the available routes and their functionalities in the Fabric Supply Chain application. It provides clear information on how to use each route and the expected responses.


