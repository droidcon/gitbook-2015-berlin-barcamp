# Reactive API - Marcel Pintó

Framework built by Netflix, port of Rx.net from Microsoft. It is based on observables that emit events that can be subcribed by subscribers.
RxAndroid is an extension of RxJava with android specific observables that allows you to observe Android view events like click, visibility change etc.
RxJava allows to compose and transform observables. RxAndroid makes it easy to define on which thread the observing and subscribing should happen.
For example you can observe on a background thread and the subscriber can observe on the ui thread.

Let's explain some of the usefuls methods that can be aplied to an observable

### Cache:
Cached observables allow it to request a cached result of the observable. This comes in handy when you subscribe to an observable in an activity and your user destorys the activity (rotation etc). When the observable finishes it cant pass its value the subscriber cuz it got destroyed. When the user comes back to the Activity the obserable gets triggered again. Now with cache it gets the cached result of the previous call which avoids duplicate calls.

### Zip:
Zip creates a new observable from 2 or more orbservables. 

### Map:
Transforms the result of an observable.

### Compose

Takes the observable an applies a several of transformations (methods)

## How to use it to interact with your API?

Knowing the conecpts and the potential of each method of rxjava you can use them to modify, transform or compose diferent object coming from your API. The next step is to use Observable to provide a "locale" cache and a blocker to avoid duplicated calls. Here you can have a small example.

``` Java
  @Override
  public Subscription getStores() {
  
    // if observable is null create it, if not means that is already created so just reuse it
    // in case that it finish we will get automatically the result once subscribed.
    if (observable == null) {
      observable = api.getStoresList()
          .compose(applySchedulers(api.getStoresList()))
          .cache();
    }
    return observable.subscribe(storesList -> {});
  }
  
  // Using generics to reuse this method.
  private <T> Observable.Transformer<T, T> applySchedulers(Observable<T> toBeResumed) {
    return observable -> observable.subscribeOn(Schedulers.io())
        .onErrorResumeNext(refreshTokenAndRetry(toBeResumed))
        .observeOn(AndroidSchedulers.mainThread())
        .map(t -> {
          // Modify or transform your object
          return t;
        });
  }
```

### Subject
Thanks to the asistance they sujest a good way to reuse observables using BeheivorSubject. With it we can always get the last item posted to the subscriver and later on clear if we don't want to use it more. Beside this one we have:

AsyncSubject: only emits the last value of the source Observable

BehaviorSubject: emits the most recently emitted item and all the subsequent items of the source Observable when a observer subscribe to it

PublishSubject: emits all the subsequent items of the source Observable at the time of the subscription

ReplaySubject: emits all the items of the source Observable, regardless of when the subscriber subscribes.

### Conclusions:

RxJava opens a new world to all developers is really extense an may seam dificult at the begging but there is a moment you will get it. Take your time to play with it and you will be able to build awesome apps.

### Links:

I recomend all Dan Lew post about RXjava he explain good tips
http://blog.danlew.net/2015/03/02/dont-break-the-chain/
4 Parts
http://blog.danlew.net/2014/09/15/grokking-rxjava-part-1/

https://www.github.com/ReactiveX/RxJava/wiki

https://www.github.com/square/retrofit

https://www.github.com/square/okhttp
