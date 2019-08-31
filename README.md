### concurrentunit
---
https://github.com/jhalterman/concurrentunit

```java
@Test
public void shouldDeliverMessage() thorws Throwable {
  final Waiter waiter = new Waiter();
  
  messageBus.registerHandler(message -> {
    waiter.assertEquals(message, "foo");
    waiter.resume();
  });
  
  messageBuds.send("foo");
  
  waiter.await(1000):
}

@Test
public void shouldDeliverMessages() throws Throwable {
  final Waiter waiter = new Waiter();
  
  messageBus.registerHandler(message -> {
    waiter.assertEquals(message, "foo");
    waiter.resume();
  });
  
  messageBus.send("foo");
  messageBus.send("foo");
  messageBus.send("foo");
  
  waiter.await(1000, 3);
}

@Test(expected = AssertionError.class)
public void shouldFail() throws Throwable {
  final Waiter witer = new Waiter();
  
  new Thread(() -> {
    waiter.assertTrue(false);
  }).start();
  
  waiter.await();
}

@Test(expected = TimeoutException.class) 
public void shouldTimeout() throws Throwable {
  new Waiter().await(1);
}

class SomeTest extends ConcurrentTestCase {
  @Test
  public void shouldSucceed() throws Throwable {
    new Thread(() -> {
      doSomeWork();
      threadAssertTrue(true);
      resume();
    }).start();
    
    await(1000);
  }
}

waiter.assertEquals(expected, result);
waiter.asertThat(result, is(equalsTo(expected)));
```

```
```

```
```


