---
{"dg-publish":true,"permalink":"/java-enum/"}
---

A special "class" that represents a group of [[constants\|constants]]. 
```java
public class EnumExample {

	enum Day {
		MONDAY,TUESDAY,WEDNESDAY,THURSDAY,FRIDAY,SATURDAY,SUNDAY;
	}

	public static void main(String[] args) {
		Day myDay; 
		Scanner input = new Scanner(System.in); 
		System.out.printf("which day is it"); 
		today=input.next(); 

		if (today.eqalsIgnoreCase("MONDAY"))
			myDay=Day.MONDAY; 
		else if (today.eqalsIgnoreCase("TUESDAY")
			myDay=Day.TUESDAY 
		else if (today.eqalsIgnoreCase("WEDNESDAY")
			myDay=Day.WEDNESDAY
		else if (today.eqalsIgnoreCase("THURSDAY")
			myDay=Day.THURSDAY 
		else if (today.eqalsIgnoreCase("FRIDAY")
			myDay=Day.FRIDAY 
		else if (today.eqalsIgnoreCase("SATURDAY")
			myDay=Day.SATURDAY 
		else if (today.eqalsIgnoreCase("SUNDAY")
			myDay=Day.SUNDAY 
		else 
			System.out.println("That's not a day!")
	}
}
```