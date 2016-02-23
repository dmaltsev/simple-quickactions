# Introduction #

I wanted to be able to use the QuickActions and Popdown menu that the Twitter for Android app features but I did not want to wait for them to open source the code. So the only option was to figure out how they did it.

The key is a little unknown class in the android.widget namespace. [PopupWindow](http://developer.android.com/reference/android/widget/PopupWindow.html) is the key. It allows you to display any arbitrary view on the screen. It does most of the work for you it just needs a little bit of massaging to have it do exactly what you want.

For the Popdown menu look it's really just a matter of having the correct animation set. You can look at the Animation.PopDownMenu in the styles.xml to see how it's done.

The QuickAction look is only slightly more complicated. It needs two animations, one for when it pops out of the top of a view, and one for when it pops down bellow the view. Then it's just a matter of computing where it should display. You can see that in BetterPopupWindow#showLikeQuickAction.

## Caveats ##

This demo code does not look like the Twitter for Android QuickActions and Popdown menu. This is intentional, as it's style dependent on the application. I left the styling alone and focused solely on the mechanics.