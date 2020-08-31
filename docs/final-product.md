# Fast track

You don't want to do the tutorial, you just want to get this demo up and running. For that follow this steps.

1. Go to the note-app folder

```
cd note-app
```

2. Initialize AWS Amplify, accept all the defaults.

```
amplify init
```

Wait for it to complete

3. Add the Auth category, accept all the defaults

```
amplify add auth
```

4. Add the API category. Select GraphQL as the API type and Amazon Cognito User Pool as the auth mechanism.

```
amplify add api
```

When it ask if you have a schema, say no. And pick the defualt until the editor opens.

You need to replace that schema with the one in this file: ../base/schema-03.graphql

5. Add the AI integration

```
amplify add predictions
```

When we are prompt a message to choose we pick "Interpret" and then "Interpret text".

Then we need to provide a friendly name for the resource. Leave the default.

Then it ask what kind of interpretation we want. We can choose all so we can see what this service return.

And when it ask for access, select the option "Auth users only".

6. Push the changes to the cloud

```
amplify push
```

7. Install the application locally

```
npm install
```

8. Start the local server

```
npm start
```

Now you can test the app, everything should be created now.
