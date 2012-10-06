---
layout: post
title: Android GCM, Retry Receiver Class Not Set Yet
truncate: false
---
I'm working on a project that needed Android push notifications and decided to use
[GCM](http://developer.android.com/guide/google/gcm/gs.html "GCM") - it's very easy
to setup. I did however run into an issue that Google has fixed in their source
repository, but hasn't been distributed to end users yet.

If you get the error "internal error: retry receiver class not set yet," then you've
got an older version of the client gcm.jar.
[This](https://code.google.com/p/gcm/source/diff?spec=svne1a099b36566c265f758facf70b8f4f3684ed0ea&r=e1a099b36566c265f758facf70b8f4f3684ed0ea&format=side&path=/gcm-client/src/com/google/android/gcm/GCMBroadcastReceiver.java "Patched GCMBroadcastReceiver")
is the patch that fixes the error.

Instead of patching your local version of GCMBroadcastReceiver.java in the
Android SDK, you can download either the source or the updated gcm.jar file
from the GCM repository.

Edit: Turns out this will be in the next [release](https://code.google.com/p/gcm/wiki/ReleaseNotes "GCM Release Notes") of GCM.

Voila!