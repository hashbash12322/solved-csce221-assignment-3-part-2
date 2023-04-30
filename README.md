Download Link: https://assignmentchef.com/product/solved-csce221-assignment-3-part-2
<br>
<h1>Problem 1</h1>

<strong>Abstract</strong>

In this assignment, we are using the Doubly Linked List ADTs that are implements as a templated Queue and Stack data structure. The Doubly Linked List consists of the header and trailer pointer and nodes that have points to the previous and next element in the list. The node contains the templated element which in this assignment is a double and a string. The algorithms used here are contained within the Parser class and the Evaluator class.

<ul>

 <li>The classes that I choose to implement were the LinkedQueue, LinkedStacked, Evaluator and Parser classes. By building upon the templated LinkedQueue and LinkedStack classes, I created the parser class which is used to convert an infix expression that the user inputs into a postFix expression that the Evaluator class will ultimately evaluate. Along the way, the Evaluator class asks the user for numerical entries if the user included variables for the infix notation. These are all called by the main file which displays the user menu and requests that the user submit the equation via keyboard input.</li>

</ul>

The reason why I choose these classes was due to the example presented in class and the logic that was behind the associated input priority and stack priority of the operators +<em>,</em>−<em>,</em>∗<em>,/,<sup>, </sup></em>(<em>,</em>)<em>. </em>The Parser class correctly sorts the input and creates an postFix notation of the input.

<ul>

 <li><strong>Parser</strong></li>

</ul>

The Parser class contains the following <strong>Private </strong>members:

<ul>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>postFixQueue; </strong>– A queue that holds the postFix notation</li>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>inFixQueue; </strong>– A queue that holds the inFix notation</li>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>tokenize(std::string input); </strong>– Takes a string as an input and converts the string into nodes that are pushed onto a LinkedQueue. If the parenthesis are not balanced, then an error is thrown and the program closes. This function returns the inFix notation. This function is</li>

</ul>

O(<em>n</em>)                                                            (1)

<ul>

 <li>linear complexity.</li>

</ul>

<ul>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>toPostFix</strong>(<em>LinkedQueue &lt; std </em>:: <em>string &gt; in</em>)<strong>; </strong>– Based on the order of precedence on the slides, this function uses the two data structures, Stack and Queue, and correctly sort and create a postFix notation of the input expression. If the user used variables in their expression, the variables are still present in the postFix notation. This function is</li>

</ul>

O(<em>n</em>)                                                            (2)

<ul>

 <li>linear complexity.</li>

</ul>

And the following <strong>Public </strong>members:

<ul>

 <li><em>Parser</em>(<em>std </em>:: <em>strings</em>) {<em>tokenize</em>(<em>s</em>);}<strong>; </strong>– The Parser constructor which call the function tokenize.</li>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>getPostFix(); </strong>– Returns the private variable PostFixQueue. This function is</li>

</ul>

O(1)                                                            (3)

<ul>

 <li>constant complexity.</li>

</ul>

Problem 1 continued on next page…

Problem 1 (continued)

<ul>

 <li><em>int </em><strong>inputPriority(string temp); </strong>– Assigns a specific value to the input operator from the string. This value is then later used by the parse to correctly place the operator in the postFix expression. This function is</li>

</ul>

O(<em>n</em>)                                                            (4)

<ul>

 <li>linear complexity.</li>

</ul>

<ul>

 <li><em>int </em><strong>stackPriority(string temp); </strong>– Assigns a specific value to the stack operator from the string. This value is then later used by the parse to correctly place the operator in the postFix expression. This function is</li>

</ul>

O(<em>n</em>)                                                            (5)

<ul>

 <li>linear complexity.</li>

</ul>

<ul>

 <li><em>bool </em><strong>isBalanced(); </strong>– This function counts the instances of the left prenthesis and right parentheses and returns a bool if the expression is balanced or not. This function is</li>

</ul>

<table width="624">

 <tbody>

  <tr>

   <td width="607">O(1)A constant complexity.• <em>void </em><strong>printInfix(); </strong>– Prints the Infix from inFixQueue. This function is</td>

   <td width="17">(6)</td>

  </tr>

  <tr>

   <td width="607">O(1)A constant complexity.• <em>void </em><strong>printPostfix(); </strong>– Prints the Postfix from postFixQueue. This function is</td>

   <td width="17">(7)</td>

  </tr>

  <tr>

   <td width="607">O(1)</td>

   <td width="17">(8)</td>

  </tr>

 </tbody>

</table>

<ul>

 <li>constant complexity.</li>

</ul>

<strong>Evaluator </strong>The Evaluator class contains the following <strong>Private </strong>members:

<ul>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>postFixQueue; </strong>– A queue that holds the postFix notation</li>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>eval; </strong>– A queue that holds the inFix notation</li>

 <li><em>double </em><strong>value; </strong>– This returns the final answer as a double.</li>

 <li><em>string </em><strong>tres; </strong>– Global string for the answer that returns from the double evaluation.</li>

 <li><em>string </em><strong>before double; </strong>– String that later gets converted to a double.</li>

</ul>

And the following <strong>Public </strong>members.

<ul>

 <li><em>Evaluator</em>(<em>LinkedQueue &lt; std </em>:: <em>string &gt; par</em>) – This is the default constructor for the Evaluator class. The input is a LinkedQueue object of strings which contains the postFix expression that will be evaluated.</li>

</ul>

Problem 1 continued on next page…

Problem 1 (continued)

<ul>

 <li><em>double </em><strong>getValue(); </strong>– This function returns the value of the final answer as a double. This function is</li>

</ul>

O(1)                                                            (9)

<ul>

 <li>constant complexity.</li>

</ul>

<ul>

 <li><em>string </em><strong>switchCase(double a, double b, string cur num); </strong>– This function will evaluate the specific operations that is requested from the postFix notation. The arguments are two strings that will be operated on. This function returns a string that will be pushed onto the stack for later operations. This function is</li>

</ul>

O(1)                                                          (10)

<ul>

 <li>constant complexity.</li>

</ul>

<ul>

 <li><em>LinkedQueue &lt; std </em>:: <em>string &gt; </em><strong>get digits(</strong><em>LinkedQueue &lt; std </em>:: <em>string &gt; in</em><strong>); </strong>– If the user submitted the expression using variables, this function will request the user to submit numerical entries for the said variables. This function returns a postFix queue that contains numbers and operators. This function is</li>

</ul>

O(<em>n</em>)                                                          (11)

<ul>

 <li>linear complexity.</li>

</ul>

<ul>

 <li>For correctness, I inputted various expression that contained illegal characters. The program caught these characters correctly and threw an error message which then ended the program. These characters were caught because I created a test with the use of ASCII characters and their acceptable ranges.</li>

 <li>Below I have demonstrated a few test cases that use illegal characters and are caught by the program. As shown, two instances of unbalanced parenthesis and illegal expressions are caught from the input, thus proving the correctness of the program!</li>

</ul>