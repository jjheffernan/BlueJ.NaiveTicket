# NaiveTicket

The second Objects lab, from the BlueJ book's second chapter.

First you need to FORK this repo into your account, then you need to CLONE that foreked repo, the one in your account. 
When you are finished with your code, be sure to ADD/COMMIT and PUSH your code to your repo.

Use the URL from your repo as the submission to the portal. 

Look for the [Chapter 2 file](./doc/BlueJ-objects-first-ch2.pdf) you need in the [doc](./doc) folder.
There is 35 pages of reading and exercises in the chapter.

Work through all these exercises. You edit this file with your answers for these exercises.

### Exercise 2.1
* Create a TicketMachine object on the object bench.
* Upon viewing its methods, `getBalance`, `getPrice`, `insertMoney`, `printTicket`.
* Use `getPrice` method to view the value of the price of the tickets that was set when this object was created.
* Use `insertMoney` method to simulate inserting an amount of money into the machine.
* Use `getBalance` to check that the machine has a record of the amount inserted.
	* You can insert several separate amounts of money into the machine, just like you might insert multiple coins or notes into a real machine. Try inserting the exact amount required for a ticket. As this is a simple machine, a ticket will not be issued automatically, so once you have inserted enough money, call the `printTicket` method. A facsimile ticket should be printed in the BlueJ terminal window.
// After Completing These steps, I have 3 Integers, price1, Balance1, Balance2 and string ticket1
### Exercise 2.2
* What value is returned if you check the machine’s balance after it has printed a ticket?
// Int Balance2 was got, and returns 0. This was after printing String ticket1
### Exercise 2.3
* Experiment with inserting different amounts of money before printing tickets.
	* Do you notice anything strange about the machine’s behavior?
 // Using the pop-up menus, its very simple to use selectively skip the "get" function and print extra tickets without impacting balance. The Machine also does not keep visual track of your balance, instead you must request balance like an ATM, not like a vending machine where it is displayed. Upon purchasing a 2nd ticket, reads a string "Ticket price: 500 cents. your Total is 1050." There was 1 previous ticket, so im unsure if the counter should tell the customer the number of sales.  
	* What happens if you insert too much money into the machine – do you receive any refund?
 // After printing ticket2, I inspected the balance, which reads 0. Meaning that the refund has disappeared, and was not addressed or returned to the user. No refund! :(   
	* What happens if you do not insert enough and then try to print a ticket?
 // If you do not insert enough money, you can still get a ticket. There is an issue with the return string when printing a ticket. The Balance for printing a ticket is from the internal ATM balance, that should go to the train station. That balance is then being used to qualify for ticket purchases, which is incorrect. It should refer to balance.

### Exercise 2.4
* Try to obtain a good understanding of a ticket machine’s behavior by interacting with it on the object bench before we start looking at how the `TicketMachine` class is implemented in the next section.

### Exercise 2.5
* Create another ticket machine for tickets of a different price.
	* Buy a ticket from that machine.
	* Does the printed ticket look different?
 // the printed ticket doesnt appear different, except for the int length of the string is 1 longer. that could be because I named them differently though. "ticket3" versus "m2ticket1" for tickets from machine 2.

### Exercise 2.6
* Write out what you think the outer wrappers of the `Student` and `LabClass` classes might look like – do not worry about the inner part.
// public class Student
    { 
    ...
    }
// public void class LabClass(int RoomNumber)
    {
    ...
    }

### Exercise 2.7
Does it matter whether we write<br>
`public class TicketMachine`<br>
or<br>
`class public TicketMachine`<br>
in the outer wrapper of a class?

* Edit the source of the `TicketMachine` class to make the change and then close the editor window.
	* Do you notice a change in the class diagram?
	* What error message do you get when you now press the compile button?
	* Do you think this message clearly explains what is wrong?
 // The error within the editor reads <identifier> expected. the next line also yield an "illegal start of expression" error. The class diagram also had the unit test half shaded, and the TicketMachine class was fully red shaded. This clearly explains where and what went wrong, however it did not explicitly state that it was a misordered line.   

### Exercise 2.8
* Check whether or not it is possible to leave out the word `public` from the outer wrapper of the `TicketMachine` class.
// it is in fact possible for the code to compile, but I believe that this is bad practices because now the args wont properly run and interact. 
### Exercise 2.9
* From your earlier experimentation with the ticket machine objects within BlueJ you can probably remember the names of some of the methods – `printTicket`, for instance.
	* Look at the class definition in Code 2.1 and use this knowledge, along with the additional information about ordering we have given you, to try to make a list of the names of the fields, constructors, and methods in the `TicketMachine` class.
	* Hint: There is only one constructor in the class.
 //fields: price (int), balance (int), total (int).
 //constructors: TicketMachine
 //Methods: getPrice(), getBalance(), insertMoney(int), printTicket

### Exercise 2.10
* Do you notice any features of the constructor that make it significantly different from the other methods of the class?
// The constructor often shares the same name as the class itself, unlike other methods.
### Exercise 2.11
* What do you think is the type of each of the following fields?

```java
private int count; //int
private Student representative; //String, but declared as Studen
private Server host; //String or enum, but declared as Server
```

### Exercise 2.12
* What are the names of the following fields?

```java
private boolean alive; //alive
private Person tutor; //tutor
private Game game; //game
```
### Exercise 2.13

In the following field declaration from the TicketMachine class<br>

```java
private int price;
```
does it matter which order the three words appear in?
* Edit the `TicketMachine` class to try different orderings. After each change, close the editor.
	* Does the appearance of the class diagram after each change give you a clue as to whether or not other orderings are
possible?
	* Check by pressing the compile button to see if there is an error message.
	* Make sure that you reinstantiate the original version after your experiments!
//When redordering, the error "unknown type" results, or "illegal start of argument." The test also returns half shaded, and the TicketMachine returns red fully shaded. 
### Exercise 2.14
* Is it always necessary to have a semicolon at the end of a field declaration?
* Once again, experiment via the editor.
* The rule you will learn here is an important one, so be sure to remember it.
// In Java, it is imperative to always feature a semicolon (;) at the end of a field declaration.

### Exercise 2.15
* Write in full the declaration for a field of type `int` whose name is `status`.
```java
private int status;
```

### Exercise 2.16
* To what class does the following constructor belong?

```
public Student(String name) //this constructor belongs to class Student
```

### Exercise 2.17
* How many parameters does the following constructor have and what are their types?
```
public Book(String title, double price) // There are two parameters, String "title" and double "price"
```

### Exercise 2.18
* Can you guess what types some of the `Book` class’s fields might be?
* Can you assume anything about the names of its fields?
//some fields for `Book` would be "title" and "price." They would consist of type String and double price. I could see additional doubles for rating, and an integer for page number. Potentially even a boolean for if the book is checked out in the use case of a library.
READ upto and INCLUDING section 2.15 of this chapter.
