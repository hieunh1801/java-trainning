# @DeprecatedExample

```java
package annotation_example;

public class AnnotationExample {

	public static void main(String[] args) {
		System.out.println("----------- Ví dụ về Annotation trong Java -----------");
		DeprecatedAnnotationExample deprecatedAnnotationExample = new DeprecatedAnnotationExample();
		deprecatedAnnotationExample.Greeting("Hello World");
	}

	
}

class DeprecatedAnnotationExample {
	/**
	 * @deprecated thay thế bởi {@link #SuperGreeting(String,Date)}
	 * <p> 
	 * được sử dụng để đánh dấu method hoặc class ta không nên sử dụng nữa.
	 * <p>
	 * ==> Lý do: vì nó danger hoặc có một method tương ứng xử lý ngon hơn.
	 * ==> Thông thường ta sẽ comment xem có method nào thay thế nó không.
	 */
	@Deprecated
	public void Greeting(String greeting) {
		System.out.println("Hello World");
	}
	
	public void SuperGreeting(String greeting) {
		System.out.println("SuperGreeting");
	}
}
```