---
title: "Advance"
bg: '#188FA7'
color: white
fa-icon: rocket
---
## Advance Initialization

* Only if you wanna add Custom Encryption Methods.

{% highlight text linenos=table %}
       new SecurePrefManagerInit.Initializer(getApplicationContext())
               .useEncryption(true)
               .setCustomEncryption(new Encryptor(getApplicationContext()) {
                   @Override
                   public String encrypt(String s) throws Exception {
                       // Your Encryption Algorithm
                       return encryptedString;
                   }

                   @Override
                   public String decrypt(String s) throws Exception {
                       // Your Decryption Algorithm
                       return decryptedString;
                   }
               })
               .initialize();
{% endhighlight %}

## Custom Encryptors.


{% highlight text linenos=table %}
public class CustomEncryptor extends Encryptor {



    public CustomEncryptor(Context context) {
        super(context);

    }


    public BlowFishEncryptor(Context context, String encryptionKeyPhrase) {
        super(context, encryptionKeyPhrase);

    }


    @Override
    public String encrypt(String value) throws Exception {
    	// Encrypt data here
        return encrypted String;
    }

    @Override
    public String decrypt(String encryptedValue) throws Exception {
     	// Decrypt data here
        return decrypted String;
    }
}
{% endhighlight %}

## Preference Hiding (EXPERIMENTAL)

Now hide your Preference from others.

* Hide preference when leaving the activity.

{% highlight text linenos=table %}

@Override
protected void onPause() {
    SecurePrefManager.with(getApplicationContext())
            .hide(new HidePreferences.PreferenceUpdateListener() {
                @Override
                public void onFailure() {

                }

                @Override
                public void onProgress(int p, int max) {

                }

                @Override
                public void onSuccess() {

                }
            });
}

{% endhighlight %}

* Unhide Preferences when the activity starts

{% highlight text linenos=table %}

@Override
protected void onStart() {
    super.onStart();
    SecurePrefManager.with(getApplicationContext())
            .unhide(new HidePreferences.PreferenceUpdateListener() {
                @Override
                public void onFailure() {
 
                }

                @Override
                public void onProgress(int p, int max) {
  
                }

                @Override
                public void onSuccess() {
                	// Start Using Preferences aftr this.
                }
            });
 }

{% endhighlight %}

### Have Fun!

