# Stfalcon ImageViewer (Forked by Hsnaimeh)

[![JitPack](https://jitpack.io/v/Hsnaimeh/StfalconImageViewer.svg)](https://jitpack.io/#Hsnaimeh/StfalconImageViewer)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

A modernized and forked version of the original **Stfalcon ImageViewer**, now fixed for JitPack compatibility and simplified for Android developers. It supports full-screen image viewing with shared transitions, pinch-to-zoom, and swipe-to-dismiss gestures.

Compatible with popular libraries like **Picasso**, **Glide**, etc.

![Main Demo](images/image_viewer_main_demo.gif) ![Transition Demo](images/image_viewer_transition_demo.gif)

---

## 🚀 Installation (via JitPack)

### Step 1: Add JitPack to `settings.gradle` (or `build.gradle` project-level)

```gradle
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        maven { url 'https://jitpack.io' }
    }
}
```

### Step 2: Add the dependency to your module `build.gradle`

```gradle
dependencies {
    implementation 'com.github.Hsnaimeh:StfalconImageViewer:v1.0.7'
}
```

---

## 📱 Usage

### Simple Example

```kotlin
StfalconImageViewer.Builder<Image>(context, images) { view, image ->
    Picasso.get().load(image.url).into(view)
}.show()
```

### With Transition

```kotlin
StfalconImageViewer.Builder(context, images, ::loadImage)
    .withTransitionFrom(imageView)
    .show()
```

### Update Images Dynamically

```kotlin
viewer.updateImages(newImagesList)
```

### Jump to Specific Image

```kotlin
viewer.setCurrentPosition(index)
```

### Add Overlay View

```kotlin
viewer.setOverlayView(customOverlayView)
```

### Customize Viewer

```kotlin
StfalconImageViewer.Builder(context, images, ::loadImage)
    .withStartPosition(0)
    .withBackgroundColor(Color.BLACK)
    .withOverlayView(view)
    .withImagesMargin(R.dimen.image_margin)
    .withContainerPadding(R.dimen.padding)
    .withHiddenStatusBar(true)
    .allowZooming(true)
    .allowSwipeToDismiss(true)
    .show()
```

---

## ✅ Requirements

* AndroidX project
* minSdkVersion 19+

---

## 🧪 Sample Project

This fork **excludes the sample module** to ensure clean JitPack builds. You can check the original sample here:
[Sample from original repo](https://github.com/stfalcon-studio/StfalconImageViewer/tree/master/sample)

---

## 💬 Contact

This fork is maintained by [Hisham Sanimeh](https://github.com/Hsnaimeh).

---

## 📜 License

```
Copyright (C) 2018 stfalcon.com

Licensed under the Apache License, Version 2.0 (the "License");
You may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
