# rxAndroid
1. <b>debounce</b> example
- incremental, last location, last text changed ....
```val obs = RxTextView.textChanges(username_login).filter { charSequence -> charSequence.length > 3 }.debounce(300, TimeUnit.MILLISECONDS).map { charSequence -> charSequence.toString() }
obs.subscribe { string ->
    Log.d(this::class.java.simpleName, "debounced " + string)
}
