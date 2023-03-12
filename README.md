# Long_tv_with_Scroll
## 1. always have an linear layout or contraint layout inside of scroll view then put anything to it (text or image)
   [Documentation](https://developer.android.com/reference/android/widget/ScrollView)
## 2. if parent layout is linear layout then dont use layout gravity center in text view inside scroll view 
## 3. Should use scroll view with Relative layout or contraint layout IF text is too long
here tested found that scroll view with linear layout does not work </br>
so insterad use relative layout
first set relative layout then image layout then scrool view then text view then image view 2


<details><summary>Code</summary>
<p>

```.xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">


    <ImageView
        android:id="@+id/imageView4"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:contentDescription="@string/pic_1"
        android:src="@drawable/icons8_github_256"
        android:backgroundTint="@color/white"
        />

    <ScrollView
        android:id="@+id/scrollView"
        android:layout_width="match_parent"
        android:layout_height="300dp"
        android:layout_below="@id/imageView4"
        >

        <TextView
            android:id="@+id/textView"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textSize="14sp"
            android:text="@string/some_text" />
    </ScrollView>

    <ImageView
        android:id="@+id/imageView3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:src="@drawable/java"
        android:layout_below="@+id/scrollView"/>

</RelativeLayout>
```
</p>
</details>


<details><summary>VIDEO</summary>
<p>

https://user-images.githubusercontent.com/52217208/217413425-e2c4d6ac-cb25-4a06-8a74-b6bd2a7ffccd.mp4
</p>
</details>

