# Testing With Scala

This series assumes usage of a Scala testing library called [ScalaTest](https://www.scalatest.org/)

* The central concept in ScalaTest is the suite, a collection of zero to many tests.
* A test can be anything with a name that can start and either succeed, fail, be pending, or canceled.
* ScalaTest offers style traits that extend Suite and override lifecycle methods to support different testing styles.

## Setup

1. Put unit tests in `src/test/scala`
2. Put integration tests in `src/it/scala`
3. Put e2e tests in `src/e2e/*`
4  Put load tests in `src/load/scala`

Run your tests with `sbt test` or `sbt it:test` for integration tests.

## Testing Styles

ScalaTest supports many different styles of testing. Learn about the different styles here:
https://www.scalatest.org/user_guide/selecting_a_style

## Unit Testing

Testing individual functions of code with no external integrations.  This may require some mocking or stubbing. See the `Mocking` section at the end.

Example of a Scala Unit test in ScalaTest using the AnyWordSpec:
  
```scala  
    class IntegrationSetTest extends AnyWordSpec {
    
      val setDatabaseStub = mock[SetRepository]
      val setService = new SetService(setDatabaseStub)
      
      "A Set" when {
        "empty" should {
          "have size 0" in {
            assert(setService.retrieve("testSet").size == 0)
          }
    
          "produce NoSuchElementException when head is invoked" in {
            assertThrows[NoSuchElementException] {
              setService.retrieve("testSet").get
          ...
```
Notice that only one service is tested (SetService) with any dependencies mocked (SetRepository).
            
## Integration Testing

Testing combined functions sometimes with code that you don't control, or modules with some external integration or mocked integration.

Example of a Scala Integration test in ScalaTest:

```scala    
    class IntegrationSetTest extends AnyWordSpec {
    
      val setDatabaseStub = mock[SetRepository]
      val setService = new SetService(setDatabaseStub)
      val setRoute = new SetRoutes(setDatabaseStub)
          
      "A Set" when {
        "empty" should {
          "return an empty response" in {
            assert(setRoute.view("testSet").response == Response(Set()))
          }
          ...
```

Notice that two code modules are in play with any other dependencies mocked (SetRepository).
We are testing both the actual SetService and the SetRoutes together.

## E2E Testing

End To End testing is critical as it tests the full journey of data in our service from database to response from the user's perspective. 
These tests can rely on test containers with an ad hoc test database or a persistent test database or event test data in Production.
In order to run against test data in Production your team needs to have robust Code Review processes and controls in place.

Postman, Insomnia, Python or even Bash scripts are useful tools to build E2E tests and run automatically with a CICD pipeline.

## Performance Testing

Performance testing has 3 major phases:
1. Load Testing
2. Stress Testing
3. Soak Testing

Performance testing is done with [Gatling](https://gatling.io/docs/current/)

Here is an example of load testing an API:
```scala 
    class HeadstormLoad extends Simulation {
    
      val httpProtocol = http
        .baseUrl("https://prod.headstorm.com") // Here is the root for all relative URLs
        .acceptHeader("application/json;") // Here are the common headers
        .acceptEncodingHeader("gzip, deflate")
    
      val scn = scenario("Load Test") // A scenario is a chain of requests and pauses
        .exec(
          http("Load Test API")
            .get("/load-me")
        )
    
      setUp(scn.inject(constantUsersPerSec(100) during (30 seconds)).protocols(httpProtocol))
    }
```
    
Download Gatling [here](https://gatling.io/open-source/)

## Mocking

Mocking allows us to emulate dependencies in our tests without constructing them from scratch. 
The Mocking tool used with ScalaTest is called [ScalaMock](https://scalamock.org/)

You saw examples above in the Unit and Integration tests for usage. Here is how you might create a mock that would be used as shown above:
```scala 
      // Create mock SetRepository object
      val mockedTurtle = mock[SetRepository]
     
      // Set expectations
      (mockedTurtle.addItem _).expects(Item(...))
      (mockedTurtle.getItem _).expects(Item(...))
      (mockedTurtle.removeItem _).expects(Success()).returning(()))
```
The last 3 lines of code set expectations for how the generated Mock SetRepository should behave under test.

# Fixtures

Fixtures are 
```scala 
    def fixture =
       new {
         val builder = new StringBuilder("ScalaTest is ")
         val buffer = new ListBuffer[String]
       }
   
     "Testing" should "be easy" in {
       val f = fixture
       f.builder.append("easy!")
       assert(f.builder.toString === "ScalaTest is easy!")
       assert(f.buffer.isEmpty)
       f.buffer += "sweet"
     }
```
## Testing Data Integrity

TODO

## Test Containers

TODO

## Automating Tests with CICD

TODO