# Expo Camera takePictureAsync returns null uri

This repository demonstrates a bug in the Expo Camera API where the `takePictureAsync` method returns a photo object with a null `uri` property, even though the image has been successfully captured.  This prevents the image from being displayed or processed further.  The bug is particularly noticeable when using custom camera settings.

## Bug Description

When using the Expo Camera API with custom camera settings (such as setting aspect ratio or flash mode), the `takePictureAsync` method sometimes returns a photo object with the `uri` property set to null.  This happens despite the fact that the image appears to have been captured successfully.  The console log shows the photo object with other properties populated (like width, height, etc.), but `uri` is absent or null.

## Solution

The solution involves adding error handling and checking for the existence of the `uri` before attempting to use it. It also includes a check to ensure that the photo object is not null before accessing its properties.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install` or `yarn install`.
3. Run the app on a physical device or simulator.
4. Attempt to take a picture.
5. Observe the console log and the app's behavior.  The image may not display, and the console log will show the issue.

## Additional Notes

This bug seems to be intermittent and may not occur every time.  The frequency of the issue might be related to device specifics, Expo version, or other factors.