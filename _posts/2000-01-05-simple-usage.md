---
title: "Simple"
bg: '#63BD2F'
color: white
fa-icon: plug
---


##Initialize SecurePrefManager anywhere before using it.



* Basic Initialization

{% highlight text linenos=table %}
       new SecurePrefManagerInit.Initializer(getApplicationContext())
               .initialize();
{% endhighlight %}

*  Recommended Initialization
	* AES Encryption by Default.
	* Auto Generated Key.

{% highlight text linenos=table %}
       new SecurePrefManagerInit.Initializer(getApplicationContext())
               .useEncryption(true)
               .initialize();
{% endhighlight %}


### Adding and Retrieving Preferences

* Adding
{% highlight text linenos=table %}
        SecurePrefManager.with(this)
                .set("user_name")
                .value("LoremIpsum")
                .go();
{% endhighlight %}

* Retrieving

{% highlight text linenos=table %}
        String userName = SecurePrefManager.with(this)
                .get("user_name")
                .defaultValue("unknown")
                .go();
{% endhighlight %}

