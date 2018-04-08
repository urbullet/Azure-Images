# Azure-Images
An Android library that handles Microsoft Azure's Image Upload in Async and Synchronized methods,
without needing to start an Async Task like the official documentation suggests.


Add these files to your build.gradle (Module:app) folder

    implementation 'io.reactivex.rxjava2:rxandroid:2.0.1'
    // Because RxAndroid releases are few and far between, it is recommended you also
    // explicitly depend on RxJava's latest version for bug fixes and new features.
    implementation 'io.reactivex.rxjava2:rxjava:2.1.7'

To use the library is very straight to the point, simply call the ImageManager instance and choose wether to upload the image in 
the background or synchronous. 

* Uploading in the background : (put the image as base64 and pass it to the method, and a new listener to handle what happens when upload
is complete.

        ImageManager.uploadImageAsync(base64Encoded, url -> {
            if (url != null) {//if upload is successful
                photo.setPhoto(url);
                sendPhotoRequest(photo);
            }
        });
