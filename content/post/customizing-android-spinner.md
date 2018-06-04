---
title: "Customizing Android Spinner"
date: 2018-06-03T05:12:29+08:00
draft: false
tags: ["tutorials", "android", "custom spinner", "spinner bold tex", "spinner text size"]
---
In this article, we will be customizing the android spinner widget so that we can control its content's style. Note that the IDE used here is Android Studio, but you can use whatever you prefer and familiar with.

## Part 1 : Creating and Android Project Using Android Studio

Let's start by creating our project.

<img src="/images/customizing-android-spinner/android_studio_start.png" alt="Android Studio" width="400" />

Select **Start a new Android Studio Project**

<img src="/images/customizing-android-spinner/create_android_project.png" alt="Android Studio" width="500" />
Fill the necessary inputs with your preference. You may check the **Include Kotlin support** checkbox if you want but in this tutorial, we are going to be using Java as the programming language. Click **Next**.

In the screen below, I selected the API 15 to support most of the android devices.
<img src="/images/customizing-android-spinner/selecting_api.png" alt="Selecting Android API" width="500" />
Click **Next**.

In the next screen, select either *Blank Activity* or *Empty Activity* then hit **Next**.
<img src="/images/customizing-android-spinner/select_activity.png" alt="Android Studio" width="500" />

Type in the activity name and the layout name then hit **Finish**.
<img src="/images/customizing-android-spinner/activity_name.png" alt="Android Studio" width="500" />

Let's now edit the layout file on the **res** directory of the Android Explorer.
<img src="/images/customizing-android-spinner/layout_file.png" alt="Android Studio" width="400" />

## Part 2 : Creating the Custom Spinner

This is the original code generated by Android Studio. Let's replace the *TextView* with *Spinner* to work on our project.

*Listing 2-1 : activity_main.xml*
```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</android.support.constraint.ConstraintLayout>
```

*Listing 2-2 : activity_main.xml (updated)*
```xml
<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Spinner
        android:id="@+id/spinnerId"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

    </Spinner>

</android.support.constraint.ConstraintLayout>
```

Now, what we really want to do to achieve the customization of the spinner widget content is to create a customized TextView to be used by our spinner.
Let's now create a new file in the **res** directory named *spinner_text.xml* and put in the code below.

*Listing 2-3 : spinner_text.xml*
```xml
<?xml version="1.0" encoding="UTF-8"?>
<TextView
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:textSize="24sp"
    android:textStyle="bold"/>
```

Please note that what special we did here is to make the text bold and with size of 24sp. This customization is not available on the default spinner widget that's why we need to come to this process.

Now that the layout and custom text for spinner is ready, let's now implement it on the app.

On the *MainActivity.java* file:

*Listing 2-4 : MainActivity.java*
```Java
package com.alexiusacademia.customspinner;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
}

```

Let's now create an array of strings to hold array of texts that our spinner will contain. In this method, we are using Java to create the array, we can also use an xml resource but it will be on a different tutorial.

```Java
@Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Array of strings
        String[] texts = {
                "German Shepherd",
                "Labrador Retriever",
                "Bulldog",
                "Poodle",
                "Beagle",
                "Golden Retriever",
                "Chihuahua",
                "Pug"
        };
```

To access the spinner widget on the layout, let's refer to it using:

```Java
"Beagle",
        "Golden Retriever",
        "Chihuahua",
        "Pug"
};

Spinner spinner = findViewById(R.id.spinnerId);
```

Let's now customize the array adapter for the spinner.
```Java
};

Spinner spinner = findViewById(R.id.spinnerId);

ArrayAdapter<String> adapter = new ArrayAdapter<>(this, R.layout.spinner_text, texts);
adapter.setDropDownViewResource(R.layout.spinner_text);
spinner.setAdapter(adapter);
```
Note that the adapter specifies the custom text that we made for the spinner, *spinner_text.xml*.

Now run the app and you should see a screen similar to this when you tapped on the spinner:
<img src="/images/customizing-android-spinner/customized_spinner.png" alt="Customized Android Spinner" width="300" />

That's all for today and thank you for reading.