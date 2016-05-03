**Android PDFView** is a library by Joan Zapata which provides a fast PDFView component for Android, with ```animations```, ```gestures```, and ```zoom```. It's based on [VuDroid](https://code.google.com/p/vudroid/) for decoding the PDF file.

This fork adds some functionality. [Click here](https://github.com/JoanZapata/android-pdfview) to be redirected to Joan's main repository.

# Get it

Get it with Jitpack:

```groovy
allprojects {
	repositories {
		maven { url "https://jitpack.io" }
	}
}

dependencies {
	compile "com.github.aurae:android-pdfview:-SNAPSHOT"
}
```

# Include PDFView in your layout

```xml
<com.joanzapata.pdfview.PDFView
        android:id="@+id/pdfview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
```

# Load a PDF file

```java
pdfView.fromAsset(pdfName)
    .pages(0, 2, 1, 3, 3, 3)
    .defaultPage(1)
    .showMinimap(false)
    .enableSwipe(true)
    .useChangingPageDimensions(false)
    .onDraw(onDrawListener)
    .onLoad(onLoadCompleteListener)
    .onPageChange(onPageChangeListener)
    .load();
```

* ```pages``` is optional, it allows you to filter and order the pages of the PDF as you need
* ```useChangingPageDimensions``` is optional, it allows you to load PDF files containing pages with differing dimensions
* ```onDraw``` is also optional, and allows you to draw something on a provided canvas, above the current page

# License

```
Copyright 2013-2015 Joan Zapata

This file is part of Android-pdfview.

Android-pdfview is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

Android-pdfview is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with Android-pdfview.  If not, see <http://www.gnu.org/licenses/>.
```
