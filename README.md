# Long_tv_with_Scroll
## 1. Scrollview ---> linearLayout or constraintlayout ---> have your textview or imageview
If you have more than ONE VIEW then have your textview or imageview under any layout not directly to the scroll view

in short more than one view should not be direct child of scroll view

As per [Documentation](https://developer.android.com/reference/android/widget/ScrollView)
   
<details><summary>Code1</summary>
<p>

```.xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="10dp"
    tools:context=".NewsDetailActivity">

    <com.google.android.material.imageview.ShapeableImageView
        android:id="@+id/newsImage"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:scaleType="centerCrop"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.842"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.03"
        app:srcCompat="@drawable/img1">

    </com.google.android.material.imageview.ShapeableImageView>

    <com.google.android.material.textview.MaterialTextView
        android:id="@+id/newsHeading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:gravity="start"
        android:text="Joe Biden appoints two prominent......"
        android:textSize="23sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.526"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/newsImage"
        app:layout_constraintVertical_bias="0.03">

    </com.google.android.material.textview.MaterialTextView>

    <ScrollView
        android:layout_width="376dp"
        android:layout_height="200dp" //or 0dp but not match parent or wrap content
        android:layout_marginTop="12dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.742"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/newsHeading"
        app:layout_constraintVertical_bias="0.177">
        >

        <androidx.constraintlayout.widget.ConstraintLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content">
            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="@string/news_content"
                app:layout_constraintStart_toStartOf="parent"
                app:layout_constraintEnd_toEndOf="parent"
                app:layout_constraintTop_toTopOf="parent"
                app:layout_constraintBottom_toBottomOf="parent">
            </TextView>
            
            //Your other view HERE 

        </androidx.constraintlayout.widget.ConstraintLayout>
    </ScrollView>
</androidx.constraintlayout.widget.ConstraintLayout>
```
</p>
</details>

## 2. Should use scroll view with Relative layout or contraint layout IF text is too long
here tested found that scroll view with linear layout does not work </br>
so insterad use relative layout
first set relative layout then image layout then scrool view then text view then image view 2


<details><summary>Code2</summary>
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

## 3. If parent layout is linear layout then dont use layout gravity center in text view inside scroll view 

<details><summary>VIDEO</summary>
<p>

https://user-images.githubusercontent.com/52217208/217413425-e2c4d6ac-cb25-4a06-8a74-b6bd2a7ffccd.mp4
</p>
</details>

