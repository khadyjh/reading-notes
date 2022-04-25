#  Intents, Activities, and SharedPreferences

## Save key-value data 

to save key-value data in android java you need to use SharedPreferences APIs 


SharedPreferences object acts like pointer points to files containing **key-value pairs and provides simple methods to read and write them.** Each SharedPreferences file is managed by the framework and can be private or shared.


- getSharedPreferences() 
 
  Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.

- getPreferences()

   Use this from an Activity if you need to use only one shared preference file for the activity. Because this retrieves a default shared preference file that belongs to the activity, you don't need to supply a name.


   **The name for SharedPreferences file should be unique to your app**

**you can write to the SharedPreferences file using  putInt() and putString(). Then call apply() or commit() to save the changes**

**you can read from the SharedPreferences file using   getInt() and getString() , and provide the key for the value you want**





# Tasks and the back stack

A task is a collection of activities that users interact with
when you start the app for the first use the main activity is called and pushed to the stack , then when another activity called well pushed to the top of the stack, and so on 

 when the back button is called the activity users in will be destroyed and popped off the stack , but the main activity never popped out off the stack 

 ![backStack](./imges/diagram_backstack.png)

**Main Activity**

Root launcher activities are activities that declare an Intent filter with both **ACTION_MAIN** and **CATEGORY_LAUNCHER.** These activities are unique because they act as entry points into your app from the app launcher and are used to start a task.


  resources :

 [sharedpreferences](https://developer.android.com/training/data-storage/shared-preferences)

 [Tasks and the back stack](https://developer.android.com/guide/components/activities/tasks-and-back-stack)