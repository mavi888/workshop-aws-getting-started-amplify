# Add authentication

Now that we have a simple React app, let’s let users sign up and sign in to our app. They won’t be able to do anything yet, but it will be helpful to have this in place so that when we add in the ability to query our backend API, we’ll know which users are accessing our system.

Here’s what the sign-in screen will look like:

<img src="../images/app-signin-screen.png"
     alt="Preview of the login screen" />

## Setting up the backend

1. Run amplify add auth to add authentication to the app

```
amplify add auth
```

2.  Select "Default Configuration" when asked if you’d like to use the default authentication and security configuration

3.  Select "Username" when asked how you want users to sign in.

4.  Select “No, I am done.” when asked about advanced settings.

5.  Run amplify push to create these changes in the cloud

```
amplify push
```

6. Confirm you want Amplify to make changes in the cloud for you.

7. Wait for the provisioning to complete. This will take a few minutes.

The Amplify CLI will take care of provisioning the appropriate cloud resources and it will update src/aws-exports.js with all of the configuration data we need to be able to use the cloud resources in our app.

Amazon Cognito lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily. We just made a User Pool, which is a secure user directory that will let our users sign in with the username and password pair they create during registration. Amazon Cognito (and the Amplify CLI) also supports configuring sign-in with social identity providers, such as Facebook, Google, and Amazon, and enterprise identity providers via SAML 2.0. If you’d like to learn more, we have a lot more information on the [Amazon Cognito Developer Resources](https://aws.amazon.com/cognito/dev-resources/) page as well as the [AWS Amplify Authentication documentation](https://aws-amplify.github.io/amplify-js/media/authentication_guide#federated-identities-social-sign-in).

## Setting up the frontend

Now we will change a bit the look and feel of our application.

You can copy the files:

```
cp ../base/App-02.js src/App.js
cp ../base/App-02.css src/App.css
```

Now after we refresh our page should look something like this:

<img src="../images/app-signin-screen.png"
     alt="Preview of the login screen" />

If you check in the App.js file you will see that we imported these modules:

```
import { AmplifyAuthenticator, AmplifySignOut } from '@aws-amplify/ui-react';
```

And the used them as tags in the application

```
 <AmplifyAuthenticator>
      <div className="row">
        <div className="col m-3">
          <Header/>
        </div>
      </div>
</AmplifyAuthenticator>
```

## Creating an account

1. You can now create a new user using that page and log in to the application.

Note: Use a real email address as you are going to recieve a mail with a validation code

Note: Don't forget the password as we will be using this account during our workshop

2. Check your email. You should have received a confirmation code message.

Copy and paste the confirmation code into your app and you should then be able to log in with the username and password you entered during sign up.

After you log in this is what you will see:
<img src="../images/first-look-note-app.png"
     alt="Preview of the noteapp screen" />
