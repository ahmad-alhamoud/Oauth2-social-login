# Spring boot OAuth2 Social Login

A sample project that shows how to implement OAuth2 login using Google and Github as a resource server.

### let’s discover who plays roles in an OAuth 2 system

1 - **The user**: the person who uses the application. The users usually work
with a frontend application which we call a client. The users don’t
always exist in an OAuth 2 system.

2 - **The client**: the application that calls a backend needs
authentication and authorization. The client can be a web app, a mobile
app, a desktop app, or a separate backend service.

3 - **The resource server**: A backend application that authorizes and serves
calls sent by one or more client applications.

4 - **The authorization server**: An app that implements authentication and
safe storage of credentials.

### Application diagram

![Diagram](./diagram.png?raw=true "Diagram")

### OAuth2.0 flow (How things really work in action)

![Diagram](./oauth2-flow.png?raw=true "OAuth 2.0 flow diagram")

### Steps to create a gitHub application
* Go to [GitHub developer portal](https://github.com/settings/developers)
* Create a new application and provide the required information
  * Set the homepage URL to http://localhost:8080
  * Authorization callback URL to http://localhost:8080/login/oauth2/code/github.

### Update the `application.yml` file
After creating a new application, you will a client ID and a client secret. Copy this two information and paste the in the `application.yml` file

```
spring:
  security:
    oauth2:
      client:
        registration:
          github:
            clientId: github-app-client-id-here
            clientSecret: github-app-client-secret-here
          google:
            client-id: google-app-client-id-here
            client-secret: google-app-client-secret-here
```

### Start the application and enjoy your Social-login
