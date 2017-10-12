# Android ImageLoader
A lightweight library for developers to deal with image downloading, fast and simple!
- Fetching and displaying images with only one line of code   
- Includes image size adjustment to display it properly    
- Available on jCenter and Maven Central    
<a href="https://bintray.com/dilyar85/Android/imageloader/0.1.1">
  <img src="https://github.com/dilyar85/Android-ImageLoader/blob/master/screenshots/jfrog_logo.png" alt="View it from JFrog" width="50" height="50">
</a>

<a href="https://search.maven.org/#artifactdetails%7Ccom.github.dilyar85%7Cimageloader%7C0.1.1%7Caar>
	<img src = "https://github.com/dilyar85/Android-ImageLoader/blob/master/screenshots/maven_logo.jpg" height="50">
</a>


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


