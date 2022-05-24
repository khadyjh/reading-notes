#  Cognito 
Amazon Cognito lets you add user sign-up, sign-in,
and access control to your web and mobile apps quickly and easily.

to start using cognito first you need to set up android application integrate with amplify library 

then you need to run som command 

```
amplify add auth
```
then you need to answer this questions 

```
? Do you want to use the default authentication and security configuration?
    `Default configuration`
? How do you want users to be able to sign in?
    `Username`
? Do you want to configure advanced settings?
    `No, I am done.`
```
then you need to push the changes to the cloud by run **amplify push** in the terminal 

and add the dependency to build.gradle in app level 

```
dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.35.4'
}
```

resources

[cognito](https://docs.amplify.aws/lib/auth/getting-started/q/platform/android/)