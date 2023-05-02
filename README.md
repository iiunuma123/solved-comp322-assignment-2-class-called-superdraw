Download Link: https://assignmentchef.com/product/solved-comp322-assignment-2-class-called-superdraw
<br>



In the following questions you will be designing a class called ​<strong><em>SuperDraw​</em></strong> to generate lotto numbers and manage the process of verifying whether a ticket is a winner. Every lotto ticket has 6 numbers generated randomly between 1 and 49. A number cannot be repeated in the same ticket.

The main SuperDraw class structure should look like the following:

struct​ ​<strong>ticket</strong>

{ unsigned​ ​int​ numbers[​6​]; ticket* next;

};  class​ ​<strong>SuperDraw</strong>

{ public​:

SuperDraw();

~SuperDraw(); private​:

ticket* ticketListHead; ticket* ticketListTail; }; <em>ticket ​</em>is a linked list structure that holds the 6 lotto numbers in an array and a pointer to the next element in the list. Notice that the class SuperDraw has 2 private data members, ticketListHead and ticketListTail. They are 2 pointers pointing to the head (first element) and the tail (last element) of the linked list.

<h1>Question 1</h1>

Complete the implementation for the class ​<strong><em>SuperDraw​</em></strong> ​by implementing the constructor and the destructor bodies if needed. Constructor should be initializing the object to whatever initial suitable state.

<h1>Question 2</h1>

Add a public method called newTicket(int verbose = 0) that generates random 6 numbers. The newly created ticket should be added to the linked list and the randomly generated numbers should be printed out to the screen if verbose argument is set to 1. By default the verbose argument is set to 0 which means that no messages will be printed out to the screen.

The numbers should be sorted in ascending order.

Remember that the pointers ticketListHead and ticketListTail should be updated accordingly after the generation of each new ticket

The test main() function should look like the following:

int​ ​<strong>main</strong>​()

{

SuperDraw sd;

sd.newTicket(1);

}

The output should be something like:

<em>A new ticket was successfully generated. The numbers are: 12, 14, 23, 39, 40, 44 </em>

<em> </em>

<h1>Question 3</h1>

Add a constructor that takes an int argument which corresponds to the number of tickets to be generated.

The test main() function should look like the following:

int​ ​<strong>main</strong>​()

{

SuperDraw sd(2);

}

The output should be something like:

<em>2 new ticket were successfully generated.  </em>

<em>The numbers are: 12, 14, 23, 39, 40, 44 and 1, 2, 9, 12, 28, 41 </em>




<h1>Question 4</h1>

Add a public method called printAllTicketNumbers() that print to the screen a list of all generated numbers for all the tickets.

The test main() function should look like the following:

int​ ​<strong>main</strong>​()

{

SuperDraw sd; sd.newTicket(); sd.newTicket(); sd.newTicket(); sd.newTicket();

sd.printAllTicketNumbers();

}




The output should be something like:

<em>We found 4 generated tickets:  </em>

<em>12, 14, 23, 39, 40, 44 </em>

<em>1, 5, 12, 14, 32, 33 </em>

<em>2,24, 27, 29, 45, 46 </em>

<em>8, 12, 19, 29, 32, 34 </em>




<h1>Question 5</h1>

Add a method called verifySequence() that verifies if a certain sequence of numbers is already generated.

The test main() function should look like the following:

int​ ​<strong>main</strong>​()

{

SuperDraw sd; sd.newTicket();

// as many sd.newTicket() as you like       Int myNumbers[6] = {2, 4, 17, 29, 31, 34}       sd.verifySequence(myNumbers)

}

The output should be something like:

<em>The provided sequence of numbers was never generated before </em>

Or:

<em>The provided sequence of numbers was already generated. </em>




<h1>Question 6</h1>

Add a method called deleteSequence() that deletes a ticket. Note that in order to delete a ticket, you have to verify first whether a ticket existed, if so you need to delete it by freeing its allocated memory and then you need to update the ​<em>next ​</em>pointer of the previous element in the list that was initially pointing to it.

The test main() function should look like the following:

int​ ​<strong>main</strong>​()

{

SuperDraw sd; sd.newTicket();

// as many sd.newTicket() as you like

Int myNumbers[6] = {2, 4, 17, 29, 31, 34}

sd.deleteSequence(myNumbers)

}

The output should be something like:

<em>The provided sequence of numbers was never generated before</em>

Or:

<em>The provided sequence of numbers was successfully deleted. </em>




<h1>Question 7</h1>

Provide an implementation for the destructor method that ensures that all previously allocated tickets are freed when the object is destroyed so that we don’t risk having memory leaks after running the program.




<h1>Question 8</h1>

Provide a copy constructor that copies the content of a SuperDraw object into another object.

The test main() function should look like the following:

int​ ​<strong>main</strong>​()

{

SuperDraw sd; sd.newTicket();

// as many sd.newTicket() as you like       SuperDraw sd2(sd);       sd2.printAllTicketNumbers();

}


