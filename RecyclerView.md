# RecyclerView 
In Android, RecyclerView is an advanced and flexible version of ListView and GridView. It is a container used for displaying large amount of data sets that can be scrolled very efficiently by maintaining a limited number of views. RecyclerView was introduced in Material Design in API level 21 (Android 5.0 i.e Lollipop).


it's a view where you can scroll down and scroll out without losing data 

it's a normal view you can add it as normal UI in XML 


In Android, RecyclerView provides an ability to implement the horizontal, vertical and Expandable List. It is mainly used when we have data collections whose elements can change at run time based on user action or any network events. For using this widget we have to specify the Adapter and Layout Manager.


## Implementing your adapter and view holder
The Adapter: The adapter is the main code responsible for RecyclerView. It holds all the important methods dealing with the implementation of RecylcerView. The basic methods for a successful implementation are:

- onCreateViewHolder(): which deals with the inflation of the card layout as an item for the RecyclerView.

- onBindViewHolder():which deals with the setting of different data and methods related to clicks on particular items of the RecyclerView.

- getItemCount():which Returns the length of the RecyclerView.


 resources :

 [RecyclerView ](https://developer.android.com/guide/topics/ui/layout/recyclerview#java)