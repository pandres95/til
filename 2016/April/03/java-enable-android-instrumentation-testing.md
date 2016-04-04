# Enable Android Instrumentation Test

Once in a while, you'll need enabling a library you're developing to run automated tests, instead of making an example application. Why? Is certainly faster than the classical approach.

## How you do this?

### 1. Add dependencies.

Declare them as `androidTestCompile` libraries.

```
androidTestCompile 'com.android.support.test:runner:0.4'
androidTestCompile 'com.android.support.test:rules:0.4'
```

### 2. Set the test instrumentation runner.

The instrumentation runner is the application that will run the unit tests along with your module. In `android.defaultConfig` (or `model.android.defaultConfig.with` in experimental-gradle), set.

```
testInstrumentationRunner 'android.support.test.runner.AndroidJUnitRunner'
```

### 3. Add a unit test module.

It may be like... this!

```java

package com.launchzap.sdk.android;

import android.support.test.runner.AndroidJUnit4;
import android.test.suitebuilder.annotation.SmallTest;
import org.junit.Test;
import org.junit.Assert;
import org.junit.runner.RunWith;

/**
 * Tests that the parcelable interface is implemented correctly.
 */
@RunWith(AndroidJUnit4.class)
@SmallTest public class ParameterTestAndroidUnitTest {

    @Test public void parameter_initialize() throws Exception {
        Parameter parameter = new Parameter("parameterOne", Parameter.Type._bool);
        Assert.assertEquals("parameterOne", parameter.getName());
        Assert.assertEquals(Parameter.Type._bool, parameter.getType());
    }
}

```
