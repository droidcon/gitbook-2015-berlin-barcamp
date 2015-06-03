# Reactive API - Marcel Pintó

Framework built by Netflix, port of Rx.net from Microsoft. It is based on observables that emit events that can be subcribed by subscribers.
RxAndroid is an extension of RxJava with android specific observables that allows you to observe Android view events like click, visibility change etc.
RxJava allows to compose and transform observables. RxAndroid makes it easy to define on which thread the observing and subscribing should happen.
For example you can observe on a background thread and the subscriber can observe on the ui thread.

### Cache:
Cached observables allow it to request a cached result of the observable. This comes in handy when you subscribe to an observable in an activity and your user destorys the activity (rotation etc). When the observable finishes it cant pass its value the subscriber cuz it got destroyed. When the user comes back to the Activity the obserable gets triggered again. Now with cache it gets the cached result of the previous call which avoids duplicate calls.

### Subscriber:
Takes observable and subscribes to it.

### Zip:
Zip creates a new observable from 2 or more orbservables. 

### Map:
Transforms the result of an observable.

### Links:
https://www.github.com/ReactiveX/RxJava/wiki
https://www.github.com/square/retrofit
https://www.github.com/square/okhttp
