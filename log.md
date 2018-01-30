# 100 Days Of Code - Log

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