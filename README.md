# Lab-8_202001190


## Creating test cases for `Boa` class
```
public class BoaTest {

  @Test
  public void testIsHealthyWithFavoriteFood() {
    Boa boa = new Boa("Bob", 10, "granola bars");
    assertTrue(boa.isHealthy());
  }

  @Test
  public void testIsHealthyWithoutFavoriteFood() {
    Boa boa = new Boa("Sally", 8, "mice");
    assertFalse(boa.isHealthy());
  }

  @Test
  public void testFitsInCageWithExactLength() {
    Boa boa = new Boa("Charlie", 6, "chicken");
    assertTrue(boa.fitsInCage(6));
  }

  @Test
  public void testFitsInCageWithLargerCage() {
    Boa boa = new Boa("Lucy", 5, "rats");
    assertTrue(boa.fitsInCage(10));
  }

  @Test
  public void testFitsInCageWithSmallerCage() {
    Boa boa = new Boa("Frank", 4, "eggs");
    assertFalse(boa.fitsInCage(3));
  }
}

```
The following code consists of test cases for the Boa class. The isHealthy() method is tested using a Boa instance with and without its favorite food. Similarly, the fitsInCage(int) method is tested with three different Boa instances whose length exactly matches the cage length, is smaller, and is larger than the cage length.

## `Boa` class with the `setup()` method
Sure, here's an updated version of the BoaTest class with the setUp() method modified as requested:
```
public class BoaTest {

  private Boa jen;
  private Boa ken;

  @Before
  public void setUp() throws Exception {
    jen = new Boa("Jennifer", 2, "grapes");
    ken = new Boa("Kenneth", 3, "granola bars");
  }

  // add additional test methods here
}
```

The BoaTest class is updated to initialize two Boa objects, jen and ken, using the setUp() method with the @Before annotation. This ensures that the jen and ken objects are available to all the test methods in the class
## Adding new method and test method in `Boa` class
Sure, here's an updated version of the `Boa` class with the `lengthInInches()` method added:
```
public class Boa {
  private String name;
  private int length; // the length of the boa, in feet
  private String favoriteFood;

  public Boa (String name, int length, String favoriteFood){
    this.name = name;
    this.length = length;
    this.favoriteFood = favoriteFood;
  }

  // returns true if this boa constrictor is healthy
  public boolean isHealthy(){
    return this.favoriteFood.equals("granola bars");
  }

  // returns true if the length of this boa constrictor is
  // less than the given cage length
  public boolean fitsInCage(int cageLength){
    return this.length < cageLength;
  }

  // produces the length of the Boa in inches
  public int lengthInInches(){
    return this.length * 12;
  }
}
```
And here's a new test method `testLengthInInches()` added to the `BoaTest` class:
```
public class BoaTest {
  private Boa jen;
  private Boa ken;

  @Before
  public void setUp() throws Exception {
    jen = new Boa("Jennifer", 2, "grapes");
    ken = new Boa("Kenneth", 3, "granola bars");
  }

  @Test
  public void testLengthInInches() {
    assertEquals(24, jen.lengthInInches());
    assertEquals(36, ken.lengthInInches());
  }
}
```
Furthermore, the lengthInInches() method is added to the Boa class which returns the length of the Boa in inches. A new test method testLengthInInches() is added to the BoaTest class to test the lengthInInches() method. This method calls the lengthInInches() method on two Boa objects, jen and ken, and checks that the returned values are correct using the assertEquals() method. The @Test annotation indicates that this method should be run as a JUnit test.

After running the tests, the JUnit pane should display a green bar indicating that all tests have passed.
