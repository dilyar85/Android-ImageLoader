# Android ImageLoader
<a href="https://bintray.com/dilyar85/Android/imageloader/0.1.1">
  <img src="http://findicons.com/files/icons/820/simply_google/256/google_android_download.png" alt="Download" width="50" height="50">
</a>



A simple framework for loading online & local images in ImageView. Fast and simple.


## Usage
**To load online images:**
```
ImageLoader.getInstance().loadImageWithUrl("IMAGE_URL", "YOUR_IMAGE_VIEW");
```

**To load local images:** 
```
ImageLoader.getInstance().loadImageWithPath("IMAGE_PATH", "YOUR_IMAGE_VIEW")
```

That's right, just one line code will work.
If you want to, you can also listen the change of loading.
Just implement the `ImageLoader.CallbackListener` and override its `finishLoadingImage()` method. For example:

``` 
public class MyActivity extends Activity implements ImageLoader.CallbackListener {
	
	@Override
    protected void onCreate(Bundle savedInstanceState) {
    	...
    	ImageLoader.getInstance().setCallbackListener(this);
    	...
    }

    ...


	@Override
    public void finishLoadingImage() {

    	//Image has been displayed in ImageView now.

    }
    ...


} 
```



## Installation

```
dependencies {
    compile 'com.github.dilyar85:imageloader:0.1.1'
}
```

Do not forget to declare permission in AndroidManifest.xml
```
 <uses-permission android:name="android.permission.INTERNET"></uses-permission>
 <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"></uses-permission>
 ```



## Additional Features
This ImageLoader uses LruCache so it would not redownload the images that were recelently displayed. 
It would also crop the image to iamgeview's size before downloading, which will defenately make user save their data and make loading images fast. 



## License
Licensed under <a href="http://www.apache.org/licenses/LICENSE-2.0">Apache 2.0</a>


