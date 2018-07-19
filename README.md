<p align="center">
  <img src="https://raw.githubusercontent.com/DhamodharanJaganathan/Easy-Volley-Kotlin/master/Screenshots/android_banner.png" width="500">


# Easy-Volley-Kotlin-Android (Retry Policy Added)

Volley is an HTTP library that makes networking for Android apps easier and, most importantly, faster.

<p align="center">
  <img src="https://raw.githubusercontent.com/DhamodharanJaganathan/Easy-Volley/master/Screenshots/normal1.png" width="256" >
 </p>

## Add as dependency
This library is not yet released in Maven Central, until then you can add as a library module or use JitPack.io add remote maven url

### Add this below line in root build.gradle

```java

    allprojects {
        repositories {
            maven {
                url "https://jitpack.io"
            }
        }
    }
```
    
then add a library dependency. **Remember** to check for latest release [here](https://github.com/DhamodharanJaganathan/Easy-Volley/releases) 
                             
```java
    dependencies {
        compile 'com.github.DhamodharanJaganathan:Easy-Volley:2.0.0'
    }
```

## Example for GET method :

```java
if (InternetConnectionChecker.getInstance(this).isOnline) {
                val payload = HashMap<String, String>()
                val url = "http://httpbin.org/get?param1=hello"
                VolleyCall.getResponse(this@MainActivity, url, 0, payload, object : VolleyCallback {
                    override fun onSuccessResponse(response: JSONObject) {
                        Timber.d(response.toString())
                        Toast.makeText(this@MainActivity, response.toString(), Toast.LENGTH_SHORT).show()
                    }
                    override fun onError(result: JSONObject?) {
                        Toast.makeText(this@MainActivity, "No Response from server", Toast
                                .LENGTH_SHORT).show()
                    }
                    override fun onVolleyError(error: String) {
                        Toast.makeText(this@MainActivity, error, Toast.LENGTH_SHORT).show()
                    }
                })
            } else {
                Toast.makeText(this, "No Internet Connection", Toast.LENGTH_SHORT).show()
            }
```

## Example for POST method :    

```java
if (InternetConnectionChecker.getInstance(this).isOnline) {
                // post data (ie: form data)
                val payload = HashMap<String, String>()
                payload["name"] = "Alif"
                payload["email"] = "http://itsalif.info"
                val url = "http://httpbin.org/post"
                VolleyCall.getResponse(this@MainActivity, url, 1, payload, object : VolleyCallback {
                    override fun onSuccessResponse(response: JSONObject) {
                        Timber.d(response.toString())
                        Toast.makeText(this@MainActivity, response.toString(), Toast.LENGTH_SHORT).show()
                    }
                    override fun onError(result: JSONObject?) {
                        Toast.makeText(this@MainActivity, "No Response from server", Toast
                                .LENGTH_SHORT).show()
                    }
                    override fun onVolleyError(error: String) {
                        Toast.makeText(this@MainActivity, error, Toast.LENGTH_SHORT).show()
                    }
                })
            } else {
                Toast.makeText(this, "No Internet Connection", Toast.LENGTH_SHORT).show()
            }
```

## Example for PUT method : 

```java
if (InternetConnectionChecker.getInstance(this).isOnline) {
                // post data (ie: form data)
                val payload = HashMap<String, String>()
                payload["name"] = "Alif"
                payload["email"] = "http://itsalif.info"
                val url = "http://httpbin.org/put"
                VolleyCall.getResponse(this@MainActivity, url, 2, payload, object : VolleyCallback {
                    override fun onSuccessResponse(response: JSONObject) {
                        Timber.d(response.toString())
                        Toast.makeText(this@MainActivity, response.toString(), Toast.LENGTH_SHORT).show()
                    }
                    override fun onError(result: JSONObject?) {
                        Toast.makeText(this@MainActivity, "No Response from server", Toast
                                .LENGTH_SHORT).show()
                    }
                    override fun onVolleyError(error: String) {
                       Toast.makeText(this@MainActivity, error, Toast.LENGTH_SHORT).show()
                    }
                })
            } else {
                Toast.makeText(this, "No Internet Connection", Toast.LENGTH_SHORT).show()
            } 
```

## Example for DELETE method :

```java
if (InternetConnectionChecker.getInstance(this).isOnline) {
                val payload = HashMap<String, String>()
                val url = "http://httpbin.org/delete"
                VolleyCall.getResponse(this@MainActivity, url, 3, payload, object : VolleyCallback {
                    override fun onSuccessResponse(response: JSONObject) {
                        Toast.makeText(this@MainActivity, response.toString(), Toast.LENGTH_SHORT).show()
                    }
                    override fun onError(result: JSONObject?) {
                        Toast.makeText(this@MainActivity, "No Response from server", Toast
                                .LENGTH_SHORT).show()
                    }
                    override fun onVolleyError(error: String) {
                        Toast.makeText(this@MainActivity, error, Toast.LENGTH_SHORT).show()
                    }
                })
            } else {
                Toast.makeText(this, "No Internet Connection", Toast.LENGTH_SHORT).show()
            }
        }
```

