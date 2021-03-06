

# 100 Days Of Code - Log

Author: Danny Nielsen.

**NB: I am also using [WakaTime](https://wakatime.com/dashboard) to track my daily progress and coding habits. **

**Also, I am using [Trello](https://trello.com/b/0PbPvILj/min-digitale-l%C3%B8nseddel) to manage my tasks.**

### Day 1: January 22, 2018

**Today's Progress**: Started working on incorporating Firebase DB in my DDL app. 

**Thoughts:** Slow process at first. The DDL project is over 8 months old, so I had to upgrade a lot of configs in the Grade and build files, but now it works fine. I chose to try and go with FirebaseDB which is a NoSQL JSON-based database from Google. It looks easy to integrate and use. The data can be saved in the cloud as well.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL)

### Day 2: January 23, 2018

**Today's Progress**: Chose to switch database to RealmDB after further research. It seems to suit my needs better (local storage, quick queries, easy implementation etc.)

**Thoughts:** The RealmDB impresses me. I've done a really quick test implementation today. The goal tomorrow is to see if it's really as easy to use as I think it is. I hope so. Then it will make the migrating quick and painless. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 3: January 24, 2018

**Today's Progress**: Very slow progress today. The migration of local storage to RealmDB is more complicated than I expected.

**Thoughts:** My app uses data types not supported by Realm, and I get null objects returned when I try to pull out an object. At the same time, I have difficulty viewing the Realm server. Will look into these problems tomorrow.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 4: January 25, 2018

**Today's Progress**: Still very slow progress unfortunately. Working on viewing/debugging the Realm database.

**Thoughts:** It seems that it is not very straightforward to check the Realm Database directly on a device. You need special third party tools to check and test the database, which I think is very silly.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 5: January 26, 2018

**Today's Progress**: I decided to use and implement [Stetho](https://github.com/uPhyca/stetho-realm) to test the Realm databases. 

**Thoughts:** There is a problem with the versioning though. The Stetho Realm plugin haven't been updated in a while.

Maybe I will just use a script that pulls the Realm DB file from the device, for later use in the Realm Browser. This may seem like a better idea. It's crazy how difficult it has to be to view a simple database file in the Realm DB framework. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 6: January 27, 2018

**Today's Progress**: Major process today. The main features of RealmDB now works, and full integration with my app isn't far away.

**Thoughts:** I decided to ditch Stetho and all other third party apps to check my RealmDB. Turns out that in Android Studio 3.0, it's possible to view Device Storage directly from the IDE. That makes it possible to browse the application file, find the `.realm` file and download it directly to my computer, to open with Realm Studio. That makes it much easier to check the Realm data. I've tried to include a command in the Grade build file that does the downloading from the device automatically, but I've yet to see if it really works. 

The only problem I'm facing now, is the custom data types located in the Shift class of my app. I use `JodaTime` for easy date/time manipulation, but RealmDB doesn't directly support custom types such as this. I could use the default Java Date class, but my whole application now relies on JodaTime manipulation. I have to find a way to make an adapter or something like that, so that RealmDB can store my custom class. The date from and to are very important parts of my app. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 7: January 28, 2018

**Today's Progress**: Shifts are now also saved to the realm, and pulled from the Realm successfully.

**Thoughts:** Todays coding was great. I used custom getters and setters to make my `JodaTime` objects convert to regular `Date` objects and back when saving to the Realm DB. 

The swipe-to-delete now works as well. There is a problem when using the "Undo" functionality of the swipe-to-delete. I have temporarily disabled it. It's best that I get some real progress by eleminating the local serialization storage I used earlier, and not getting caught op in small features.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 8: January 29, 2018

**Today's Progress**: 2 out of 3 functionalities are now migrated to RealmDB in the `EditDeleteJobActivity`. 

**Thoughts:** Todays coding also went well. The last functionality to Migrate to Realm, is the deletion of jobs in the `EditDeleteJobActivity` . I am hoping to finish that in tomorrows session.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 9: January 30, 2018

**Today's Progress**: The DDL app's storage functionality is now fully migrated to Realm! Furthermore, fixed a bug that's been problematic for a long time. 

**Thoughts:** It was easy to migrate the last few edit/delete job functionalities to Realm. I even managed to fix a bug that's been there almost from the start. This is great. 
Next step is to fix a very important bug. It has something to do with the calculated pay after editing a job. This will be looked into tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 10: January 31, 2018

**Today's Progress**: I have now isolated the logic that I need to fix the bug mentioned yesterday. 

**Thoughts:** This went quick and smooth. Now I need to find a way to call the created method only when it's really needed. I will work on this tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/switch_payment_bug)

### Day 11: February 1, 2018

**Today's Progress**: The bug from yesterday is now squashed, but a new one arose instead. 

**Thoughts:** Fixing of this bug went surprisingly well. Now there should be one thing less to think about, except another bug caught my eye. This one happens when you create a shift outside of the current months pay counting period. That should make the next month include that shift, but unfortunately it doesn't. I know it has something to do with my change of a list I did yesterday. I must investigate this tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 12: February 2, 2018

**Today's Progress**: The sudden bug from yesterday is now squashed, and the app is more stable than ever! 

**Thoughts:** After studying the method from yesterday where I knew the bug originated, I found that I've been missing an important condition in one of the conditional statements in the method. The main functionality up till now has been unstable because of that, and random bugs would occur. Now, it seems as it if runs perfectly as intended, just because I fixed that single statement. That feels great! Todays work has been merged into master and pushed to the remote repo.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 13: February 3, 2018

**Today's Progress**: I didn't have a lot of time today, so I only got to researching. But now I do know what functionality to add next. 

**Thoughts:** The most pressing matters are fixed now, as two major bugs were squashed the last few days. I've now decided that it's time to implement the 'Settings' functionality in the app. The user should be able to open the settings and change things like the AM-bidrag rate, colors in the app and stuff like that. I will start implementing this tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 14: February 4, 2018

**Today's Progress**: Time wasn't in my favor today either, but I did get to create a `preferences.xml` file and fill it up with a few settings. I will hopefully be able to implement more tomorrow 

**Thoughts:** It's relatively easy to create and implement a settings activity in Android. There are a lot of nice tools available that makes the job easier. All settings are in general defined in the `preferences.xml` file, and changed values are automatically placed in `SharedPreferences` for the app to tap into when it feel like it. This shouldn't be the biggest task. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/settings)

### Day 15: February 5, 2018

**Today's Progress**: I managed to make the Settings activity work and save the specified preferences as `SharedPreferences` for use in my app. 

**Thoughts:** Today I had a lot of time on my hands, as opposed to the last few days. I successfully built the whole Settings appearance and made it successfully store the specified values. The built-in Preference helpers in the Android library made this a very simple task. Next up, I am going to make the changes reflect the calculations and main functionality in the app. This will be done tomorrow, and should be rather quick to implement. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/settings)

### Day 16: February 6, 2018

**Today's Progress**: I successfully added functionality for changing the tax rate. The change is now reflected in the apps calculations. Also, I linked my Trello board with Github, to easier track tasks. 

**Thoughts:** As I expected the above mentioned functionality was quickly implemented and is now working perfectly. Tomorrow I hope to implement the functionality for the rest of the settings. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/settings)

### Day 17: February 7, 2018

**Today's Progress**: I'm almost done with the settings functionality for the pay-counting period. Unfortunately I encountered a bug in the process.

**Thoughts:** I am hoping to squash said bug tomorrow, and finish the pay-counting period implementation. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/settings)

### Day 18: February 8, 2018

**Today's Progress**: I am now done with the Settings activity. It works as intended.

**Thoughts:** The bug I found yesterday was nowhere to be found today. My idea is to wait it out, and keep testing it to make sure it doesn't show itself. The last functionality to change the color of the app was postponed. It doesn't seem important to use my resources for this at the moment.

Tomorrow I will start improving certain functions and looks of the app.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 19: February 9, 2018

**Today's Progress**: Not a lot of progress today. It's difficult to add certain functionality due to poor code from before Realm was implemented. 

**Thoughts:** Without duplicating code, or directly writing poor code, it's difficult to implement functionality to add new jobs directly in the Edit/Delete job activity. At the moment it's done from the main activity. 

Tomorrow I will try to find a way to do this optimally, or remove the function completely. Perhaps add some helper text at the bottom of the Activity to let people know how they add jobs. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/add_job_in_editDeleteJobActivity)

### Day 20: February 10, 2018

**Today's Progress**: I found the optimal way to add the functionality for adding a job in the EditDeleteJob Activity. At the same time, I fixed some bugs related to deleting a job with attached shifts.

**Thoughts:** Today was a good day. I didn't add too much boilerplate code to be able to add new jobs in the EditDeleteJob activity. The app is now also more stable, as a few bugs were fixed. 

Tomorrow I will work on some minor design improvements that will make the app more comfortable to use. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 21: February 11, 2018

**Today's Progress**: 50% of the design improvements mentioned yesterday are done. 

**Thoughts:** Today went well. Tomorrow I will add the last 50% and finish the task. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/minor_improvements)

### Day 22: February 12, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** 

### Day 23: February 13, 2018

**Today's Progress**: 100% of the design improvements are done. 

**Thoughts:** Todays task was quickly made. Tomorrow I will find out what to prioritise next.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 24: February 14, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 25: February 15, 2018

**Today's Progress**: Bugfixes, more reliable code and improvements overall has been done today.

**Thoughts:** Today was a great day with a lot of little code changes/improvements that hopefully will end up making my app work better. I've fixed a couple of nasty bugs too. Tomorrow I will work on adding a cancel-button to selected Dialogs in the app.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 26: February 16, 2018

**Today's Progress**: Cancel buttons on all dialogs added, and improved styling in general through the app.

**Thoughts:** Today went great. I added a cancel button to all the Dialogs in the app, and improved the styling through the app quite a bit.

Tomorrow I will start by prioritising a new task. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 27: February 17, 2018

**Today's Progress**: A lot of Android Lint inspection warnings are now fixed.

**Thoughts:** Today I spent some time fixing some code and following the main code standard. The built-in Lint inspection tool in Android Studio pointed me in the direction of some modifications that could help my code.

Tomorrow I will start by prioritising a new task. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 28: February 18, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 29: February 19, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 30: February 20, 2018

**Today's Progress**: Even more Android Lint inspection warnings are now fixed.

**Thoughts:** I improved my code even more today by using the Lint inspection tool.

It's going to be hard to find the time to code for the next few days, but next time I am going to focus on testing. Mainly developing a test plan with test cases, followed by Unit tests. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 31: February 21, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 32: February 22, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 33: February 23, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 34: February 24, 2018

**Today's Progress**: More lint corrections done today, and also I've changed the app launcher name to be shorter, so it doesn't get cut off. 

**Thoughts:** Slow day with some more lint corrections and smaller changes, like the icon name. I've been very busy with schoolwork in the last period, so I really hope to pick up the pace again with this project in the next few days. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/lint_improvements)

### Day 35: February 25, 2018

**Today's Progress**: Code improvements and added labor market contribution tax in the pay calculation.

**Thoughts:** Today went well. The mentioned improvements were added rather quickly. Tomorrow I will start researching how to properly test the application thoroughly. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

###Day 36: February 26, 2018

**Today's Progress**: Thorough Android testing research and the first few Unit Tests are written.

**Thoughts:** Today I started by researching the best way to test my Android application. There are several different kinds of tests you can do. Unit testing, UI testing etc. My idea is to start by creating small unit tests that can run automatically and notify me if changes in code break the functionality. I've written the first few tests, and they pass correctly. My concerns are that right now my MainActivity holds way too much functionality logic nested in private methods throughout the class. If I should have any hopes of Unit testing these private methods, maybe I should split them up logically, and make them accessible package-wide so they can be tested properly. Tomorrow I am going to research a little, and find out if this is the best approach. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 37: February 27, 2018

**Today's Progress**: More test research. I realise now that the best idea in my project is to use the Android Espresso testing framework.

**Thoughts:** With the Espresso framework I can combine Unit tests with UI tests, to make sure that button clicks do what they are supposed to do, and that the correct elements show up on the screen.

I will dive deeper into this kind of testing tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 38: February 28, 2018

**Today's Progress**: More test research and a few more espresso tests. 

**Thoughts:** Tomorrow I will research how to properly organize my code, so that it can be Unit tested properly as well. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 39: March 1, 2018

**Today's Progress**: Bugfix and more test research. 

**Thoughts:** I fixed a bug that's been nagging me for a while, so that's nice. Tomorrow I will keep researching proper code structure. [Here](https://developer.android.com/topic/libraries/architecture/guide.html), for example.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 40: March 2, 2018

**Today's Progress**: Coding architecture research. I am getting closer to a decision of using MVP (Model-View-Presenter) in my app.

**Thoughts:** Idea for the basic app architecture (without the remote data source entity):

![app_arch](https://github.com/googlesamples/android-architecture/wiki/images/mvp.png)

[This](https://developer.android.com/topic/libraries/architecture/guide.html) basic architecture guide was a good read, [this](https://github.com/googlesamples/android-architecture/tree/todo-mvp/) sample project by Google is a very good reference on how to properly structure code. I am going to be studying this project further in order to improve my code. I know it's a lot of work to restructure my entire application in order to fit a certain architecture. I should have done it to begin with, but I was too eager to start coding back then. The process of restructuring my application is very important, as it will make it far more testable and maintainable. This is still just a hobby project, but it's also a very valuable learning tool. At the same time I would like to release this app to the AppStore, and if I want to have any hopes of a satisfied (if any) user base, then my app should be properly coded and tested. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 41: March 3, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 42: March 4, 2018

**Today's Progress**: More architecture research today, and I've started by categorizing classes and resources into folders. 

**Thoughts:** I've decided to go for MVP, but without the extensive use of interfaces. Interfaces are generally smart to use, due to polymorphism. For example, it's much easier to create mock objects when using an interface. If you have the correct implementation vs. the test implementation with fake data, an interface can be useful. However in my case, I don't have any heavy dependencies, and the RealmDB runs only local storage (for now). An interface is luckily easy to create, so I can create one later if there is use for it. For now, while I'm getting used to the MVP architecture, I would rather make sure that my code is as de-cluttered as possible. I will start by creating Presenter classes and moving code tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup)

### Day 43: March 5, 2018

**Today's Progress**: More Google MVP blueprint research today, and I've created interfaces and logic for the Realm local data sources.

**Thoughts:** I thought that it was a good idea to start isolating and specifying the RealmDB logic. It's accessed from basically anywhere in the application, so no matter where I start, I need to be able to handle the DB objects. 

Tomorrow I will implement the MVP pattern in the first app category. I think I'm going to start small, so that I get used to the pattern. I might get too confused if I start with the MainActivity (containing the most logic).

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup)

### Day 44: March 6, 2018

**Today's Progress**: Today went really well. I've successfully implemented the MVP architecture on the AddNewJob functionality, and the functionality works!

**Thoughts:** After implementing with MVP, I can really begin to see where this pattern shines. Loose coupling, testability and code maintenance is so much simpler when using this pattern.

Tomorrow I will make sure that the AddNewJob is completely functioning with MVP, and afterwards (if I have time for it) implement the MVP architecture on another functionality. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_editdeletejob)

### Day 45: March 7, 2018

**Today's Progress**: The functionality in AddNewJob is now fully MVP. 

**Thoughts:** Tomorrow I will work on adding MVP to the EditJob functionality. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_editdeletejob)

### Day 46: March 8, 2018

**Today's Progress**: The functionality in EditJob is now fully MVP. 

**Thoughts:** Tomorrow I will work on adding MVP to the last functionality in the EditDeleteJob logic. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_editdeletejob)

### Day 47: March 9, 2018

**Today's Progress**: Due to work, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_editdeletejob)

### Day 48: March 10, 2018

**Today's Progress**: Today I tested all the functionality in the EditDeleteJobs section of my app after it was all converted to MVP. It works even better than it did before, and the code is much more clean, testable and rid of as many dependencies as possible.

**Thoughts:** Tomorrow I will converting the MainActivty to MVP. This is the big one, so it's going to take some time. Fortunately, I've learned a lot by converting the lesser functionality first. Hopefully this one won't be too painful.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup)

### Day 49: March 11, 2018

**Today's Progress**: Today I've created and filled classes and interfaces for the AddShift functionality.

**Thoughts:** I will implement these methods tomorrow to make the AddShift functionality fully MVP.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup)

### Day 50: March 12, 2018

**Today's Progress**: Today went well, and the AddShift functionality is now fully following the MVP pattern.

**Thoughts:** Tomorrow It's the big one - I will create interfaces and possibly some implementations for all the functionality in the MainActivity.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup)

### Day 51: March 13, 2018

**Today's Progress**: I've started creating methods in the interface for the Main activity.

**Thoughts:** More methods will come eventually and while I replace the code, but tomorrow I am going to start implementing the methods.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_mainactivity)

### Day 52: March 14, 2018

**Today's Progress**: I've started the main presenter implementation.

**Thoughts:** Hopefully I will finish this tomorrow so I can start replacing the local methods in the MainActivity.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_mainactivity)

### Day 53: March 15, 2018

**Today's Progress**: Both the View and Presenter interfaces for the Main functioanlity are now implemented.  

**Thoughts:** I've also started by slowly replacing a couple of methods in the MainActivity. Hopefully I can finish this tomorrow, and solve the bugs that may arise. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_mainactivity)

### Day 54: March 16, 2018

**Today's Progress**: A few more methods are replaced and confirmed working fine.

**Thoughts:** Will continue replacing methods tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_mainactivity)

### Day 55: March 17, 2018

**Today's Progress**: Much of the functionality works, but I've encountered a bug I need to fix.

**Thoughts:** Hopefully this can be done tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_mainactivity)

### Day 56: March 18, 2018

**Today's Progress**: I've solved the bug from yesterday and now almost all of the functionality works! 

**Thoughts:** Tomorrow (and maybe a bit later today) I will continue to test the functionality thoroughly, and also improve the MVP and code where I see fit. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_mainactivity)

### Day 57: March 19, 2018

**Today's Progress**: More bugfixes and changes to the MVP structure. It's going really well.

**Thoughts:** Tomorrow I will delete all the out-commented redundant code and further improve the MVP on the main functionality where it can be improved. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_mainactivity)

### Day 58: March 20, 2018

**Today's Progress**: Main functionality is now fully MVP!

**Thoughts:** It took a while, but the main functionality is now also made MVP. The whole application feels smoother and better overall at the same time. No dependencies where they aren't needed, and much cleaner, testable code.

Tomorrow I will begin with the last thing that has to be made MVP - the settings functionality. That shouldn't take long. Afterwards, the whole application is built up on MVP. Then I can get along to the next functionality needed.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup)

### Day 59: March 21, 2018

**Today's Progress**: Settings functionality is now fully MVP!

**Thoughts:** The main Settings functionality is now MVP. There are some places where I simply think it's overkill to convert to MVP for the time being. I would rather focus on new functionality and fixes. When I need to further develop more functionality into the settings section, then perhaps I can continue from a MVP standpoint. 

Tomorrow I will start out by checking my Trello Board and prioritising a task. Maybe I will start out by converting the Trello list to Issues on Github instead. We'll see. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/mvp_setup_settings)

### Day 60: March 22, 2018

**Today's Progress**: Today I've implemented an About-page in the app.

**Thoughts:** I've used a library that works really well. It allows one to create beautiful About-pages with just a couple of object creations. Tomorrow I will prioritise and new task and start with that.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 61: March 23, 2018

**Today's Progress**: Minor, but significant improvements today. I've fixed a couple ToDos in the code, and most importantly I've fixed all app icons to crisper, clearer icons on all device sizes.

**Thoughts:** Android has a built-in studio for creating materialised icons of own choice. It works really well, and it has made sure that every icon inside the application is crystal clear according to the Google standards. It all looks a lot better now.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 62: March 24, 2018

**Today's Progress**: I've set a maximum and minimum year on the DatePickerDialogs when you add a Shift. Will test and merge tomorrow.

**Thoughts:** It doesn't make sense for the user to be able to enter Shifts for another year than the present one. I've fixed the ability to do that. 

Tomorrow I will test and merge the code and prioritise a new task. Thorough testing will most likely be the next task.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 63: March 25, 2018

**Today's Progress**: The maximum and minimum dates on the DatePickers are now live, but I've encountered a problem with my pay counting period algorithm. I am going to try to solve this tomorrow. 

**Thoughts:**

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 64: March 26, 2018

**Today's Progress**: I've finally fixed the bug mentioned yesterday.

**Thoughts:** Tomorrow I will start by prioritising a new task.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 65: March 27, 2018

**Today's Progress**: I've decided to fix the relative sizes and relations between the main View objects. They need to be set correct, so that every individual screen size supports the app.

**Thoughts:** I will continue working on this tomorrow.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 66: March 28, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 67: March 29, 2018

**Today's Progress**: I've made a quick fix to the RecyclerView scroll and implemented better MVP implementation for some OnDismiss handlers in the code.

**Thoughts:** Will start a new task tomorrow.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 68: March 30, 2018

**Today's Progress**: I've now started unit testing!

**Thoughts:** The tests work really well and have already helped improving my production code. I am mocking the external dependencies so that the tests are thorough. It's great!

Tomorrow I will also test as much as I possibly can.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 69: March 31, 2018

**Today's Progress**: More code improvements and stability added due to testing.

**Thoughts:** More and more ideas towards better code and more constraints are being added to my code. Testing my code thoroughly generates new ideas, it's great.

Testing will continue tomorrow.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 70: April 1, 2018

**Today's Progress**: Due to social plans, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 71: April 2, 2018

**Today's Progress**: One more Presenter class is now fully unit tested.

**Thoughts:** I will continue testing the next Presenter class tomorrow.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 72: April 3, 2018

**Today's Progress**: One more Presenter class is now fully unit tested, and I've started testing the MainPresenter class.

**Thoughts:** The MainPresenter is the biggest one, so I didn't get to test it fully today. I will continue testing it tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 73: April 4, 2018

**Today's Progress**: More tests added to the MainPresenter class. Only a couple remaining. 

**Thoughts:** I also realised that the MainPresenter class isn't the last one to unit test - I accidentally skipped EditDeleteJobPresenter, although testing that shouldn't take long.

Also I've rearranged the Trello board and learned a bit more about testing Android applications. Right now I am making small tests (Unit tests). That's what 70% of tests should be. 20% is medium tests (implementation tests) and 10% should be large tests (UI test with Espresso, for example). 

I am going to do all these kinds of tests after finishing the unit tests. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 74: April 5, 2018

**Today's Progress**: Due to illness, I unfortunately wasn't able to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 75: April 6, 2018

**Today's Progress**: Due to illness, I unfortunately wasn't able to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 76: April 7, 2018

**Today's Progress**: Due to social plans, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 77: April 8, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 78: April 9, 2018

**Today's Progress**: Due to studying, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 79: April 10, 2018

**Today's Progress**: It has been way to long away from my project due to illness and social plans, but now I'm back! All tests are now completed and passed in the MainPresenterTest. 

**Thoughts:** The code coverage is a little off (by about 14%). I think I will fix this tomorrow, before moving on to testing the last Presenter.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 80: April 11, 2018

**Today's Progress**: The MainPresenter is now about ~98% tested, and I think that will do. 

**Thoughts:** The last 2% doesn't cover any essential code. I've started testing the EditDeleteJobPresenter. That shouldn't take long. I expect to finish that tomorrow. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 81: April 12, 2018

**Today's Progress**: The EditDeleteJobPresenter is now fully tested, and that concludes (first part) Unit testing! 

**Thoughts:** It's done! All the Presenters are now fully tested and passed successfully. Look at the image below. It looks very nice. 

Tomorrow I am going to research the Google sample MVP app to check if there are any kinds of tests I missed, before I start UI testing with Espresso.

![image-20180412211136169](/var/folders/h_/h4hn40pd7vjdf7r9y1q3szym0000gn/T/abnerworks.Typora/image-20180412211136169.png)

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 82: April 13, 2018

**Today's Progress**: I successfully tested the "Add Shift" functionality with Espresso.

**Thoughts:** Espresso works really well, and it easy to learn. It's got a lot of great matchers and actions to perform on Views. Tomorrow I probably won't have time to test, as I have a wedding to attend. But the day after tomorrow I will test Intent-functionality and the "Add Job" functionalities.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/ui_testing)

### Day 83: April 14, 2018

**Today's Progress**: Due to social plans, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 84: April 15, 2018

**Today's Progress**: Due to social plans, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work:**

### Day 85: April 16, 2018

**Today's Progress**: I successfully tested the "Edit Job" functionality with Espresso.

**Thoughts:** More UI tests tomorrow.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/ui_testing)

### Day 86: April 17, 2018

**Today's Progress**: Struggling a little bit to find a specific View with Espresso. Will continue tomorrow.

**Thoughts:** 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/ui_testing)

### Day 87: April 18, 2018

**Today's Progress**: I managed to fix the problem from yesterday, and now I've successfully tested both "Delete Job" and "Add new Job" functionality with Espresso.

**Thoughts:** Tomorrow I will unit test the Settings functionality, as I missed that before moving on to UI tests. After that, I think I'm done with testing for now! Then I can move on to the last pieces of functionality before publishing the app.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 88: April 19, 2018

**Today's Progress**: I've now successfully unit tested 1 out of 2 Settings cases.

**Thoughts:** The second case is causing a few problems when testing. Tomorrow I will hopefully solve it.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/unit_testing)

### Day 89: April 20, 2018

**Today's Progress**: I've now successfully unit tested all Settings cases.

**Thoughts:** Tomorrow it's time to prioritise a new task! Only 11 days to go with the coding challenge. I realise now that I won't be able to get the app completely ready for release before being done, but that's okay. Maybe I am going to start the challenge again. I am definitely going to keep working on the DDL app! 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 90: April 21, 2018

**Today's Progress**: I've added a small fix successfully today.

**Thoughts:** Tomorrow I think I am going to start designing the "extra pay rate" function. I want it to be done right, but I am also eager to implement it, so that the app can go live. We'll find out what happens. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/master)

### Day 91: April 22, 2018

**Today's Progress**: I've decided that the extra rates are default and the specific hourly wage can be configured through settings. That is the simplest and cleanest way to do it.

**Thoughts:** I've set up the PreferenceScreen. Tomorrow I will start developing the functionality.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/extra_rates)

### Day 92: April 23, 2018

**Today's Progress**: Due to homework, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work**:

### Day 93: April 24, 2018

**Today's Progress**: I've now designed the Add Shift layout so that it also contains a Checkbox and a Spinner for the upcoming extra rates functionality.

**Thoughts:** Tomorrow I will add the default values to the Spinner and start working on the extra rate functionality. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/extra_rates)

### Day 94: April 25, 2018

**Today's Progress**: Today I've added event handlers and extra styling to the new Checkbox and Spinner.

**Thoughts:** Tomorrow I will hopefully start adding the functionality for choosing extra rates.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/extra_rates)

### Day 95: April 26, 2018

**Today's Progress**: Due to social plans, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work**:

### Day 96: April 27, 2018

**Today's Progress**: Due to social plans, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work**:

### Day 97: April 28, 2018

**Today's Progress**: Today I realised that I rushed into the extra rates functionality too quickly. Some unexpected problems arose when doing it the way I started doing. I decided to redesign the extra rates functionality, and now I'm on the right track. I've prepared the Views today.

**Thoughts:** Tomorrow I will hopefully start adding the functionality for choosing extra rates when adding a shift.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/extra_rates)

###Day 98: April 29, 2018

**Today's Progress**: Due to homework, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work**:

### Day 99: April 30, 2018

**Today's Progress**: Due to homework, I unfortunately didn't have time to work on my project today. 

**Thoughts:** 

**Link to work**:

### Day 100: May 1, 2018

**Today's Progress**: Well, the challenge is officially over. Where did the 100 days go? Today I added EventHandlers for the extra rate Spinner and EditText and started implementing the set-functionality.

**Thoughts:** This has been a great challenge. I've never thought that I could work so intensely and focused on a side-project while maintaining my studies and social life. I will have to admit that there are several times (especially recently due to exams closing in) that I've had to skip a day of coding. About ~20 times I'd guess. I know that it technically makes it the "80 days of code challenge" instead. Under normal circumstances I would extend this challenge with about 20 days until I've reached 100, but I can't put that much time aside in the next while due to exams. 

Perhaps afterwards I am going to start the challenge over and try again.

If we look at the process of my project, quite amazing things have happened: I started off by migrating the data storage from flimsy plain-text storage to robust Realm storage. I completely re-organised all my code to follow the MVP pattern for increased readability, performance, testability and extendability. I've also successfully tested all the code - both Unit tests and also Espresso UI tests. On top of that, I've made the app really robust. It's been a long time since my app has crashed. I've also added a load of improvement to the app, like a Settings page and revised design. I've never been closer to Play Store release than I am now. 

Even though the challenge is over, I am still going to be working on my app as much as I can. I've been massively inspired by this challenge, and now I really want my app to hit production!

Thank you for this great challenge.

~ Danny.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/extra_rates)