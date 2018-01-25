# 100 Days Of Code - Log

**NB: I am also using [WakaTime](https://wakatime.com/dashboard) to track my daily progress and coding habits.**

### Day 1: January 22, 2018

**Today's Progress**: Started working on incorporating Firebase DB in my DDL app. 

**Thoughts:** Slow process at first. The DDL project is over 8 months old, so I had to upgrade a lot of configs in the Grade and build files, but now it works fine. I chose to try and go with FirebaseDB which is a NoSQL JSON-based database from Google. It looks easy to integrate and use. The data can be saved in the cloud as well.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL)

### Day 2: January 23, 2018

**Today's Progress**: Chose to switch database to RealmDB after further research. It seems to suit my needs better (local storage, quick queries, easy implementation etc.)

**Thoughts:** The RealmDB impresses me. I've done a really quick test implementation today. The goal tomorrow is to see if it's really as easy to use as I think it is. I hope so. Then it will make the migrating quick and painless. 

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 3: January 24, 2018

**Today's Progress**: Very slow process today. The migration of local storage to RealmDB is more complicated than I expected.

**Thoughts:** My app uses data types not supported by Realm, and I get null objects returned when I try to pull out an object. At the same time, I have difficulty viewing the Realm server. Will look into these problems tomorrow.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)

### Day 4: January 25, 2018

**Today's Progress**: Still very slow process unfortunately. Working on viewing/debugging the Realm database.

**Thoughts:** It seems that it is not very straightforward to check the Realm Database directly on a device. You need special third party tools to check and test the database, which I think is very silly.

**Link to work:** [Den Digitale Lønseddel](https://github.com/dbdness/DDL/tree/integrate_realm)