# arravoDMS
An implementation of arravo document management systems using Node.js for the server and mongoDB

# Features
  # Authentication
- It uses JWT for authentication.
- It generates and returns a token on successful login or creation of a user.
- It verifies the token on every request to authenticated endpoints.
  # Users
- It allows creation of new users.
- It ensures no other user can be assigned the admin role (there is only one admin)
- It sets a newly created user's role category to regular by default if a valid role is not specified.
- It allows created user to edit/update their information.
- Only the admin user can update/edit other users information.
- All registered users can be retrieved by the admin user or other registered users (it doesn't return sensitive information of the users retrieved).
  # Roles
- It ensures that created users have a role defined (default role is regular).
- It ensures new roles can be created, updated and deleted by only the admin user.
- It allows only the admin user carry out CRUD operations on the roles.
  # Documents
- It allows new documents to be created/saved by users.
- It ensures all documents have an access type defined (default access type is public).
- It allows only admin users retrieve all documents regardless of the document required access type.
- It ensures private access typed documents can only be retrieved by their owners, public access typed documents can be retrieved by all users and role access typed   documents can be retrieved by ONLY users with the same role level as the document owner.
- It ensures only authenticated users can delete, edit and update documents they own and users cannot delete documents they do not own (with the exception of the     admin).
