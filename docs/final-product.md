# Fast track

You don't want to do the tutorial, you just want to get this demo up and running. For that follow this steps.

1. Go to the note-app folder

```
cd note-app
```

2. Install the application locally

```
npm install
```

3. Initialize AWS Amplify, accept all the defaults.

```
amplify init
```

Wait for it to complete.

4. Add the Auth category, accept all the defaults

```
amplify add auth
```

5. Add the API category. Select GraphQL as the API type and Amazon Cognito User Pool as the auth mechanism.

```
amplify add api
```

When it ask if you have a schema, say no. And pick the defualt until the editor opens.

You need to replace that schema with the one in this file: ../base/schema-03.graphql

6. Add the AI integration

```
amplify add predictions
```

When we are prompt a message to choose we pick "Interpret" and then "Interpret text".

Then we need to provide a friendly name for the resource. Leave the default.

Then it ask what kind of interpretation we want. We can choose all so we can see what this service return.

And when it ask for access, select the option "Auth users only".

7. Push the changes to the cloud

```
amplify push
```

8. Start the local server

```
npm start
```

Now you can test the app, everything should be created now.

9. Publish the app in the cloud

```
amplify add hosting
```

Then choose the option that says "Amazon CloudFront and S3"

Then choose the option "DEV". As we are doing this for a demo < TODO MAKE SURE THAT THIS WORKS ON EVENTENGINE>

Accept the default bucket name, index for the website, error docs for the website

10. Now we have created the configuration locally and we need to publish the app in the cloud. So we need to type:

```
amplify publish
```

That will return an URL, you can open that in the browser and you are done.

For cleaning up, follow the steps in [this doc](cleaning-up.md)
