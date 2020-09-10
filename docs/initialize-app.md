# Initialize the application with AWS Amplify

The AWS Amplify CLI makes it easy for us to add cloud capabilities to our web and mobile apps, with SDKs available for React and React Native, iOS, and Android.

To get started, we’ll create a new application. We’ll then wire things up in our app using the open-source AWS Amplify JavaScript library, which the AWS Amplify CLI will take care of configuring for us; all we have to do is use it in our React app.

AWS Amplify contains some nice abstractions for working with cloud services, and it has some helpful React components we’ll use in our app.

## Initializing Amplify

1. On the command line, in the notes-app directory. Make sure that you are in the right directory. Run:

```
amplify init
```

2. Press Enter to accept the default project name ‘notesapp’

3. Prese enter for the default environment name 'dev'

4. Select None - as we are using Cloud9

5. Choose JavaScript and React when prompted

6. Accept the default values for source directory path, distribution directory path and build command, start command

7. Select Yes when asked if you want to use an AWS profile.

8. Select the default profile when prompted

This should look something like this:

```
notes-app $amplify init

Scanning for plugins...
Plugin scan successful

Note: It is recommended to run this command from the root of your app directory

? Enter a name for the project notesapp
? Enter a name for the environment dev
? Choose your default editor: None
? Choose the type of app that you're building javascript
Please tell us about your project
? What javascript framework are you using react
? Source Directory Path:  src
? Distribution Directory Path: build
? Build Command:  npm run-script build
? Start Command: npm run-script start
Using default provider  awscloudformation

For more information on AWS Profiles, see:
https://docs.aws.amazon.com/cli/latest/userguide/cli-multiple-profiles.html

? Do you want to use an AWS profile? Yes
? Please choose the profile you want to use default
```

9. Wait until it finish creating the project in the cloud

## Installing AWS Amplify libraries

1. The first step to using Amplify in the client is to install the necessary dependencies:

```
npm install aws-amplify @aws-amplify/ui-react
```

The aws-amplify package is the main library for working with Amplify in your apps. The @aws-amplify/ui-react package includes React specific UI components we’ll use as we build the app.

2. Next, we need to configure Amplify on the client so that we can use it to interact with our backend services.

Open src/index.js and add the following code below the last import:

```
import Amplify from "aws-amplify";
import awsExports from "./aws-exports";
Amplify.configure(awsExports);
```

Or you can just copy the file from the base folder that has the changes:

```
cp ../base/App-01.js src/App.js
```

And that’s all it takes to configure Amplify. As you add or remove categories and make updates to your backend configuration using the Amplify CLI, the configuration in aws-exports.js will update automatically.

### Next...

[Add authentication](add-authentication.md)
