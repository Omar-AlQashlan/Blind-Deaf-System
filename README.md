# Mobile Application

The Mobile application convert speech into video with sign language.

## Programm we used to Code the Mobile Application
* android studio
    * Java

## Problems
1. it was hard to play multiple videos after one another in case the user say sentence.
## The Solution
1. create multiple objects  from VideoView.
2. give them the same id.
3. create action listener for each object.
```java

object.setOnCompletionListener(new MediaPlayer.OnCompletionListener() {
    @Override
    public void onCompletion(MediaPlayer mediaPlayer) {
        
    }
});
```
4. write your code.
___

## Links 

* [android studio](https://developer.android.com/studio?gclid=CjwKCAjw-8qVBhANEiwAfjXLrjQJdW2A-m3QFZwlrDGsDsZVYPDdY7SxlBh-T4R56h60XwTWiNJCbhoCUDQQAvD_BwE&gclsrc=aw.ds)

