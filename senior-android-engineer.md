# Senior Android Engineer



Design a simple android app with two screens that will display contents from a REST API.



**Screen 1** - Will show a vertical scrolling list of widgets. Each widget, depending on its type, will show one or more image. Data for this screen has to be fetched from the API-1.



Following are the list of widgets to be supported by the app:



#####  A) Image Widget



This widget can show up to three images in a row. A row occupies the full width of the screen and each image in a row should be considered as a column having equal width. It is important to preserve the aspect ratio of the image and the entire widget should have a height based on the ratio.  



Following are the configuration attributes to be supported by this widget:

1) *type* - Type of the widget.

2) *images* - Array or images to display. 

3) *cols* - Number of columns.



Each image has the following configuration attributes:

1) *width* - Width of the image.

2) *url* - URL of the image.

3) *format* - The format of the image.



#####  B) Slider Widget



A slider widget shows a slideshow of images. Each slide will occupy the entire width of the screen. The user should be allowed to slide only one image at a time. Should support automatic slide change after every 3 seconds. When the user is performing the action of sliding, disable the automatic slide change which should be resumed after the user action has completed. As always, preserve the aspect ratio of the image.



Following are the configuration attributes to be supported by this widget:

1) *type* - Type of the widget.

2) *images* - Array or images to display (Each image has the attributes mentioned above). 

3) *show* - Number of images to show in a slide (1 always).



#####  C) Carousel Widget



A carousel widget displays a carousel of images. Carousel is not the same as a slider. While a slider shows one image at a time, a carousel can show multiple images. A carousel should always have a free motion (horizontally), unlike the slider. 



Following are the configuration attributes to be supported by this widget:

1) *type* - Type of the widget.

2) *title* - Title to be displayed above the carousel.

3) *url* - Url to fetch the list of images (Each image has the attributes as defined above). 

4) *show* - Number of images to show.



**Screen 2** - Clicking on any of the widgets should open Screen 2 that will list a two column grid of images. Fetch the content necessary for this screen from the API-2.



#### Note:



1) You are free to use any 3rd party libraries for Image caching/ Network etc.
2) We encourage you to build this Android app in Kotlin.
3) Application should have a well-defined architecture such as MVP/ MVVM/ Clean.
4) Use Android Material Design Components/ Layouts.
5) It is important to deliver a good UI experience - Ensure a smooth and responsive UI even in devices with less processing power. Show proper loaders/ progress for Image loading/ API calls etc (if applicable).
6) Images can be of the format JPEG, PNG, GIF and WebP.
7) REST APIs used for this challenge will work using HTTP/ HTTPS schemes.
8) Unit tests are mandatory with over 85% of code coverage.
9) UI tests are not mandatory but a plus to have.
10) Identify and plug any memory leaks.
11) Should cover edge cases related to API parsing, missing attributes, improper attribute types, network issues etc.


[*Learn more about what our engineers do at Namshi Tech Blog*](https://tech.namshi.io/)
