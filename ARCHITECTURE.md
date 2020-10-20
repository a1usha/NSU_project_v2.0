### This file contains information about implementation details of our project (Sub modules, Use-cases, etc.)
---

Mobile app
---

Developer: Dmitry Zaikov

Default android application, it displays number of free sandbags in lounges. It sends requests to the server at regular intervals and gets information about the amount of free seats, then the app refreshes indicators on the map.

---

#### Use cases

**Choose the floor**  
*Goal*: floor changed  
*Actors*: User, Application  
*Main success scenario*:  
1) User clicks button with necessary floor number  
2) Floor map changes to floor with this number


**Watch the number of free seats**  
*Goal*: user saw quantity of free seats  
*Precondition*: user chose floor   
*Actors*: User, Application  
*Main success scenario*:  
1) User drags the map to the point with lounge
2) User sees the number of free seats

**Refresh indicators**  
*Goal*: application refreshed information about free seats  
*Actors*: Application, Server  
*Main success scenario*:  
1) Application sends request to the server
2) Server sends dictionary with ids of lounges and numbers of its free seats
3) Application refreshes information on indicators

---

Backend
---
Developer: Yakovlev Arthur

The server is the connecting link that keeps connections with users, answering their requests, and also periodically asks the ML model about the current state of the sandbags.

---

#### Use cases

**Update sandbags state**  
*Goal*: sandbags state updated.  
*Actors*: Backend, ML model.  
*Main success scenario*:  
1) It’s time to check the current sandbags state.
2) Call ML models to get the current state.
3) Update the current state in the database.

**Return the sandbag's last state**  
*Goal*: Android app got the last state.  
*Actors*: Backend, Application  
*Main success scenario*:  
1) Android app makes request to get last sandbags state
2) Backend gets last known info from the database
3) Converts it into the necessary format
4) Returns HTTP response. 

---

ML model
---
Developers: Ushaev Aleksandr, Krichevskaya Valerie

One of the key elements of our system. Responsible for detection of free and occupied bagchairs in an image or video. The model will be biult using [transfer learning method](https://en.wikipedia.org/wiki/Transfer_learning#:~:text=Transfer%20learning%20(TL)%20is%20a,when%20trying%20to%20recognize%20trucks.) - use already trained (mostly called pre-trained) convolution network as the starting point for their own model (use pre-trained weights as the initial weights for own model). More info in our [sub-repository](https://github.com/a1usha/bag-chair-model)


