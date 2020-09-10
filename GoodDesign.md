* Make your types immutable , [here are the benifits](https://dzone.com/articles/immutable-data-structures-in-java-2)
* Abstract classes  & Interface
  * Consider using abstract classes if any of these statements apply to your situation:
     * You want to share code among several closely related classes.
     * You expect that classes that extend your abstract class have many common methods or fields or require access modifiers other than public (such as protected and private).
     * You want to declare non-static or non-final fields. This enables you to define methods that can access and modify the state of the object to which they belong.
   * Consider using interfaces if any of these statements apply to your situation:
     * You expect that unrelated classes would implement your interface. For example, the interfaces Comparable and Cloneable are implemented by many unrelated classes
     * You want to specify the behavior of a particular data type, but not concerned about who implements its behavior
     * You want to take advantage of multiple inheritances
 * [Concreate Example of Command Pattern](https://www.javacodegeeks.com/2019/09/command-design-pattern-in-java.html)
 * [Example of Request Interceptor](https://kafka.apache.org/0100/javadoc/org/apache/kafka/clients/producer/ProducerInterceptor.html)
   * Kafka `ProducerInterceptor` intercept the request before sent to the Kafka server.
   * `Configurable` interface  allows to configure the `ProducerInterceptor` with values needed to function. `Configurable` interface useful when plugins are instantiated by reflection with default constuctor & initialized later with generic map of key/values
 * Well-known principle of the OOP called Composition over Inheritance, which states that "classes should achieve polymorphic behavior and code reuse by their composition (by containing instances of other classes that implement the desired functionality) rather than inheritance from a base or parent class."
   * ![composition and aggregation](https://atomicobject.com/uploads/archive/images/UML_CompositionAggregation.png)
   * More info (https://atomicobject.com/resources/oo-programming/object-oriented-aggregation)
 
