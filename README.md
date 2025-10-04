Poem Codelab exercise
This is a solution to part of the Codelab exercise

Includes:

IntelliJ setup
JPA dependencies
Lombok
Junit 5
Postgres drivers
Test containers
Is created for Java 17 corretto

Endpoints
Overview

Architecture branch
The architecture branch has been refactored to use a layered architecture. This can offer a better separation of concerns and make the code more maintainable. However, it could easily be even more elaborate, but this is a good start. For one thing, it needs tests. DAO test and Rest endpoint tests would be nice.

If you want to clone the architecture branch, you can do so with the following command:

  git clone --branch architecture https://github.com/jonbertelsen/poems.git
Helpful links and resources
The Poem API Security Exercise
Useful snippets
Token Security Library
Thomas' solution that we can copy/paste from
Security branch
This branch has been refactored to include security. It uses the TokenSecurity library. This can be used to secure other APIs as well. You will need to copy these files:

The whole security package

The pom.xml dependencies used for security.

jbcrypt
jitpack.io repository
TokenSecurity
config.properties with the secret key for jwt should be in the resources folder. Since we don't want to expose the file on Github, you need to to create it yourself and add this into it:

SECRET_KEY=4c9f92b04b1e85fa56e7b7b0a34f2de4f5b08cd9bb4dfe8ac4d73b4f7f6ef37b
ISSUER=Dit navn
TOKEN_EXPIRE_TIME=1800000
The utils package

The startServer method in the Application class

The generalExceptionHandler and apiExceptionHandler method in the ApplicationConfig class

Add the User and Role entity classes to the HibernateConfig file

Lastly, you need to add Role.EVERYONE, ROLE.USER, and ROLE.ADMIN to the endpoints. Check how it is done in the SecurityRoutes class.

