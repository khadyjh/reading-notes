# Notifications
## Allowing Other Apps to Start Your Activity
activities interact with each other using intent , To allow other apps to start your activity ,
you need to add an <intent-filter> element in your manifest file for the corresponding <activity> element.

In order to define which intents your activity can handle,each intent filter should be as specific as possible in terms of the type of action and data the activity accepts.

- Action :

  A string naming the action to perform. Usually one of the platform-defined values such as ACTION_SEND or ACTION_VIEW.
  Specify this in your intent filter with the <action> element. The value you specify in this element must be the full string name for the action, instead of the API constant 
- Data :

  A description of the data associated with the intent.
  Specify this in your intent filter with the <data> element. Using one or more attributes in this element, you can specify just the MIME type, just a URI prefix, just a URI scheme, or a combination of these and others that indicate the data type accepted.
- Category :

  Provides an additional way to characterize the activity handling the intent, usually related to the user gesture or location from which it's started. There are several different categories supported by the system, but most are rarely used. However, all implicit intents are defined with CATEGORY_DEFAULT by default.
  Specify this in your intent filter with the <category> element.


**Implicit Intents** do not directly specify the Android components which should be called, it only specifies action to be performed. A Uri can be used with the implicit intent to specify the data type.

for example
```
Intent intent = new Intent(ACTION_VIEW,Uri.parse("http://www.google.com"));
```

**Explicit Intents** are used in the application itself wherein one activity can switch to other activity

```
Intent intent = new Intent(this,Target.class);
```

resources

[Intent types](https://developer.android.com/guide/components/intents-filters#Types)

[Intent Filters](https://developer.android.com/training/basics/intents/filters)