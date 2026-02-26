## 6.2.4 Extra Mile
Update the token generator program to accept the start and stop values as command line parameters.
```java
//OpenCRXToken.java
import java.util.Random;
import java.util.Scanner;

public class OpenCRXToken {

  
  public static void main(String args[]) {
	Scanner scanner = new Scanner(System.in);
	int length = 40;
	System.out.print("Enter the start value:");
	long start = scanner.nextLong();

	System.out.print("Enter the stop value:");
	long stop = scanner.nextLong();
	scanner.close();

	String token = "";

	for (long l = start; l < stop; l++) {
	token = getRandomBase62(length, l);
	System.out.println(token);
	}
}

public static String getRandomBase62(int length, long seed) {
    String alphabet = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz";
    Random random = new Random(seed);
    StringBuilder s = new StringBuilder();
    for (int i = 0; i < length; i++) {
        s.append(alphabet.charAt(random.nextInt(62)));
    }  

    return s.toString();
}
}
```
