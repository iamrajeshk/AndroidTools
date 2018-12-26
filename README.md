# Using android studio's tools attributes for quick design review

Do you know layout tools attributes? Android Studio supports a variety of XML attributes in the tools namespace that enable design-time features. We import it sometimes without really knowing what it is for.

```
xmlns:tools="http://schemas.android.com/tools"
```
Tools namespace is used to enable design-time and complie time features.When you build your app, the build tools remove these attributes so there is no effect on your APK size or runtime behavior. 
We use `tools:text`(Use it if not already, than hard coding text with `android:text` for design checks) with a plain text or with a label from `strings.xml` file. That's it. Do you know that actually tools attribute is very powerful and can be helpful while designing?

## Show Time!!

#### Fragment
* `tools:layout` This attribute is used only by <fragment> tags and informs editor about the layout that should be drawn by layout preview inside the fragment. 
  
  ##TODO Images
  ```xml
  <fragment android:layout_width="match_parent"
              android:layout_height="match_parent"
              android:id="@+id/fragment"
              tools:layout="@layout/fragment_layout"/>
  ```

#### RecyclerView

* `tools:listitem`  This attribute allows us to replace the randoms lines of a “List Item” into a "Real Item" we have built for the actual application, directly shows inside the editor.
* `| tools:listheader | tools:listfooter` You can use these attributes to set header and footer layouts of a ListView.
* `tools:itemCount`  You can adjust the size of the list item.
 ```xml
  <android.support.v7.widget.RecyclerView
            android:layout_width="match_parent"
            android:layout_height="0dp"
            app:layout_constraintTop_toTopOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintEnd_toEndOf="parent"
            tools:listitem="@layout/sample_card_view_item"
            tools:itemCount="3"
            app:layout_constraintBottom_toBottomOf="parent"/>
  ```
#### "@tools:sample/" resources
  These are the most useful resources to inject placeholder data or images into our views. Currently, Android Studio offers following types of predefined data that can be injected into our view elements.
  
  

| Attribute value        | Description of placeholder data           |
| ------------- |:-------------:|
|@tools:sample/full_names	|  Full names that are randomly generated from the combination of |@tools:sample/first_names and |@tools:sample/last_names. |
|@tools:sample/first_names	|  Common first names. |
|@tools:sample/last_names	|  Common last names. |
|@tools:sample/cities	    |  Names of cities from across the world. |
|@tools:sample/us_zipcodes	|   Randomly generated US zipcodes. |
|@tools:sample/us_phones	|       Randomly generated phone numbers with the following format: (800) 555-xxxx. |
|@tools:sample/lorem	    |        Placeholder text that is derived from Latin. |
|@tools:sample/date/day_of_week	| Randomized dates and times for the specified format. |
|@tools:sample/date/ddmmyy |    |
|@tools:sample/date/mmddyy |    | 
|@tools:sample/date/hhmm | |
|@tools:sample/date/hhmmss | |
|@tools:sample/avatars	   |        Vector drawables that you can use as profile avatars. |
|@tools:sample/backgrounds/scenic |	Images that you can use as backgrounds. |
