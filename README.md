Download Link: https://assignmentchef.com/product/solved-cs271-assignment-5
<br>
Write and test a <em>MASM</em> program to perform the following tasks:

<ol>

 <li>Introduce the program.</li>

 <li>Get a user <em>request</em> in the range [<em>min </em>= 10 .. <em>max </em>= 200].</li>

 <li>Generate <em>request</em> random integers in the range [<em>lo </em>= 100 .. <em>hi </em>= 999], storing them in consecutive elements of an <em>array</em>.</li>

 <li>Display the list of integers before sorting, 10 numbers per line.</li>

 <li>Sort the list in descending order (i.e., largest first).</li>

 <li>Calculate and display the median value, rounded to the nearest integer.</li>

 <li>Display the sorted list, 10 numbers per line.</li>

</ol>

<strong> </strong>

<strong>Requirements</strong>:

<ol>

 <li>The title, programmer’s name, and brief instructions must be displayed on the screen.</li>

 <li>The program must validate the user’s request.</li>

 <li><em>min</em>, <em>max</em>, <em>lo</em>, and <em>hi</em> must be declared and used as global <u>constants</u>. Strings may be declared as global variables or constants.</li>

 <li>The program must be constructed using procedures. At least the following procedures are required: A. main

  <ol>

   <li>introduction</li>

   <li>get data {parameters: <em>request</em> (reference)}</li>

   <li>fill array {parameters: <em>request</em> (value), <em>array</em> (reference)}</li>

   <li>sort list {parameters: <em>array</em> (reference), <em>request</em> (value)}</li>

   <li>exchange elements (for most sorting algorithms): {parameters: <em>array</em>[i] (reference), <em>array</em>[j] (reference), where <em>i</em> and <em>j</em> are the indexes of elements to be exchanged} F. display median {parameters: <em>array</em> (reference), <em>request</em> (value)}</li>

   <li>display list {parameters: <em>array</em> (reference), <em>request</em> (value), <em>title</em> (reference)}</li>

  </ol></li>

 <li>Parameters must be passed by value or by reference <u>on the system stack</u> as noted above.</li>

 <li>There must be just one procedure to display the list. This procedure must be called twice: once to display the unsorted list, and once to display the sorted list.</li>

 <li>Procedures (except main) should not reference .data segment variables by name. <em>request</em>, <em>array</em>, and titles for the sorted/unsorted lists should be declared in the .data segment, but procedures must use them as parameters.  Procedures may use local variables when appropriate.  Global <u>constants</u> are OK.</li>

 <li>The program must use appropriate addressing modes for array elements.</li>

 <li>The two lists must be identified when they are displayed (use the <em>title</em> parameter for the <em>display</em> procedure).</li>

 <li>The program must be fully documented. This includes a complete header block for the program and for each procedure, and a comment outline to explain each section of code.</li>

 <li>The code and the output must be well-formatted.</li>

 <li>Submit your text code file (.asm) to Canvas by the due date.</li>

</ol>

<h1>page 1 of 2</h1>

<strong>Extra Credit </strong>(Be sure to describe your extras in the program header block)<strong>:</strong>

<ol>

 <li>Display the numbers ordered by column instead of by row.</li>

 <li>Use a recursive sorting algorithm (e.g., <em>Merge Sort</em>, <em>Quick Sort</em>, <em>Heap Sort</em>, etc.).</li>

 <li>Implement the program using floating-point numbers and the floating-point processor.</li>

 <li>Generate the numbers into a file; then read the file into the array.</li>

 <li>Others?</li>

</ol>

<strong> </strong>

To ensure you receive credit for any extra credit options you did, you must add one print statement to your program output PER EXTRA CREDIT which describes the extra credit you chose to work on. You will not receive extra credit points unless you do this. The statement must be formatted as follows…




–Program Intro–

<h2>**EC: DESCRIPTION –Program prompts, etc—</h2>




<strong> </strong>

<strong>Notes</strong>:

<ol>

 <li>The <u>Irvine library</u> provides procedures for generating random numbers. Call <em>Randomize</em> <u>once</u> at the beginning of the program (to set up so you don’t get the same sequence every time), and call <em>RandomRange</em> to get a pseudo-random number.  (See the documentation in Lecture slides.)</li>

 <li>The <em>Selection Sort</em> is probably the easiest sorting algorithm to implement. Here is a version of the descending order algorithm, where <em>request</em> is the number of <em>array</em> elements being sorted, and <em>exchange</em> is the code to exchange two elements of <em>array</em>:</li>

</ol>

<strong> </strong>

<strong>for(k=0; k&lt;request-1; k++) { </strong>

<strong> i = k; </strong>

<strong> for(j=k+1; j&lt;request; j++) { </strong>

<strong>  if(array[j] &gt; array[i]) </strong>

<strong>   i = j; </strong>

<strong> } </strong>

<strong> exchange(array[k], array[i]); </strong>

<strong>} </strong>

<ol start="3">

 <li>The median is calculated after the array is sorted. It is the “middle” element of the sorted list.  If the number of elements is even, the median is the average of the middle two elements (may be rounded).</li>

</ol>

<strong> </strong>

<strong>Example</strong> (user input is in <strong><em>italics</em></strong>)<strong>:</strong>

<strong> </strong>

<strong>Sorting Random Integers               Programmed by Road Runner This program generates random numbers in the range [100 .. 999], displays the original list, sorts the list, and calculates the median value.  Finally, it displays the list sorted in descending order. </strong>

<strong> </strong>

<strong>How many numbers should be generated? [10 .. 200]: <em>9</em> </strong>

<strong>Invalid input  </strong>

<strong>How many numbers should be generated? [10 .. 200]: <em>16</em> </strong>

<strong> </strong>

<strong>The unsorted random numbers: </strong>

<strong>680 329 279 846 123 101 427 913 255 736 </strong>

<strong>431 545 984 391 626 803 </strong>

<strong> </strong>




<strong>The median is 488.  </strong>

<strong>The sorted list: </strong>

<strong>984 913 846 803 </strong>

<strong>391 329 279 255 736 680 626 545 431 427 123 101 </strong>