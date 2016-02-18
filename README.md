# Animation Item List
Para poder animar un elemento de nuestra lista, este debe ser por medio del Adapter, aplicando el siguiente codigo:
```java
public void animate(ViewHolder viewHolder) {
    //-->FORMA NO.1 USANDO: https://github.com/cimi-chen/EaseInterpolator
    Interpolator interpolator = new EaseSineInInterpolator();
    Animation anim = new TranslateAnimation(1000, 0, 0, 0);
    anim.setDuration(500);
    anim.setInterpolator(interpolator);

    //-->FORMA NO.2 USANDO ANIMACIONES XML
    final Animation animAnticipateOvershoot = AnimationUtils.loadAnimation(context, R.anim.bounce_interpolator);
    viewHolder.itemView.setAnimation(anim);
}
```

###Animations in XML:
* Anim In
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/bounce_interpolator">
    <translate
        android:fromYDelta="-100%p"
        android:toYDelta="0%p"
        android:duration="800"/>
</set>
```
* Anim Out
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:fromYDelta="0%p"
        android:toYDelta="100%p"
        android:duration="@android:integer/config_shortAnimTime"/>
    <alpha
        android:duration="200"
        android:fromAlpha="1.0"
        android:toAlpha="0.0" />
</set>
```
* Fade In
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >

    <alpha
        android:duration="1000"
        android:fromAlpha="0.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:toAlpha="1.0" />

</set>
```
* Fade Out
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:fillAfter="true" >

    <alpha
        android:duration="1000"
        android:fromAlpha="1.0"
        android:interpolator="@android:anim/accelerate_interpolator"
        android:toAlpha="0.0" />

</set>
```
* Push Left In
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate android:fromXDelta="100%p"
        android:toXDelta="0"
        android:duration="300"/>
    <alpha android:fromAlpha="0.0"
        android:toAlpha="1.0"
        android:duration="1000" />
</set>
```
* Anticipate Over Shoot
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/anticipate_overshoot_interpolator">
    <translate
        android:fromYDelta="-50%p"
        android:toYDelta="0"
        android:duration="2000"
        />
</set>
```
* Bounce Interpolator
```java
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
    android:interpolator="@android:anim/bounce_interpolator">
    <translate android:fromXDelta="100%p"
        android:toXDelta="0"
        android:duration="500"/>
</set>
```
