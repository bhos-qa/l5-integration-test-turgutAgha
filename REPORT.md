## Learning Outputs
The practice of evaluating the interface between two software modules or units is known as integration testing.
It focuses on detecting if the interface is correct.
Integrity testing is used to identify issues with how integrated units interact with one another.
Integration testing is carried out following the unit testing of all the components.

## Implementation
The code snippet illustrates the process of integration testing. It simply creates HttpEntity with needed headers and sends it with GET request.
Acquired response is compared with expected one.
```
TestRestTemplate restTemplate = new TestRestTemplate();
HttpHeaders headers = new HttpHeaders();

void test(String url, String expected) throws JSONException {
    HttpEntity<String> entity = new HttpEntity<>(null, headers);
    ResponseEntity<String> response = restTemplate.exchange(
            url,
            HttpMethod.GET, entity, String.class);
    JSONAssert.assertEquals(expected, response.getBody(), false);
}
```

## Setup
The following steps are required for testing.

- Add execute permission for gradlew
```    
chmod +x gradlew
```
- Build Gradle
```
./gradlew build
```
- Run Integration Test
```
./gradlew test
```