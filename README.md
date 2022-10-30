# Sort-Visualizer-using-Python
This tool helps us to visualise sorting algorithms in our specified time speed. It also has the ability to be implemented in any code editors or for every version of python which has tkinter in it. I have implemented Bubble sort, Merge sort, Insertion sort and Selection sort with this tool.

# METHODOLOGY
This project’s code starts with basic import statements for importing the needed modules like tkinter, time and random.
•	Tkinter – Python’s GUI module
•	Time – Used for doing specific functions related to time
•	Random – Used for randomization and creating random values with specific conditions
Tkinter works by starting a tcl/tk interpreter under the covers, and then translating tkinter commands into tcl/tk commands. The main window and this interpreter are intrinsically linked, and both are required for a tkinter application to work.

Creating an instance of Tk initializes this interpreter and creates the root window. If you don't explicitly initialize it, one will be implicitly created when you create your first widget.

I don't think there are any pitfalls by not initializing it yourself, but as the zen of python states, "explicit is better than implicit". Your code will be slightly easier to understand if you explicitly create the instance of Tk. It will, for instance, prevent other people from asking the same question about your code that you just asked about this other code.

Then we have given the background colour for the window and also the size/resolution needed for it as1920x1080. Then we are creating an algorithm list consisting of 
•	Merge Sort 
•	Selection Sort 
•	Bubble Sort 
•	Insertion Sort
And then we are are using the StringVar function
The Tkinter StringVar helps you manage the value of a widget such as a Label or Entry more effectively. To create a new StringVar object, you use the StringVar constructor like this:

string_var = tk.StringVar(container, value, name)
(we create this for both algo_list and speed_list value)

After that we are creating another list for time which has values like Fast, Medium and slow for the sorting speed. And then we implement an empty array called arr.

We can see that we implemented a function called displayArr(). This function is used for creating vertical bars according to the value present in the array. This program uses a canvas window in it to show the vertical bars to be sorted. It is noted that this canvas is already been created before calling this displayArr function. The canvas.delete(« all ») will clear and delete every item in the canvas before calling this method. We give the heigth and width for the canvas window. We then calculate the width of each vertical bar and the arr (argument) array includes some of the random numbers to be given as the value for the veritical bars. Inside the for loop we create every single vertical bar with the specific width and height and also by using canvas.create_rectangle(x1, y1, x2, y2, fill=colorArray[i]) we create it with the plot parameters and colors passed into it. We use root.update_idletasks() to update the tasks.

Next we have the createArr() function. This function is used for generating the array which will be used for creating the vertical bars  (you can change array size and range as you wish) Then we add 20 more random values in the range of 20-150 to the array . We didn ‘t include 0-20 in the range because the bar will be very small to look at. Then we passed the array with the colour code which is blue to the diaplayArr() function.

Next we have the set_speed function to calculate and set the time of sorting algorithm and after the give the value in GUI this function will set the time value for the sort.

The functions merge and merge_sort are used for the merge sort algorithm visualization. Basically what they do is, it divides the array into two parts with the middle value and then further till the array values breakes down to single values and then it used the merge function to sort it back to the fully sorted array. Also called divide and conquer method. This figure shows the way it divides and merges the array.

                            



And then we have the sort function. This function has all the other sorts. First of all. It gets the time from the set_time function and then if the input from GUI is checked by the get() function. If the input is a ‘Merge Sort’ then it passes the arr, the starting and ending index, displayarr (for creating the canvas) and then the time factor to the merge_sort function automatically. This will display the algorithm with merge sorting.
And if the input from GUI is a ‘Selection Sort’. We use the algorithm for a selection sort. The selection sort algorithm sorts an array by repeatedly finding the minimum element (considering ascending order) from unsorted part and putting it at the beginning. The algorithm maintains two subarrays in a given array. 
1) The subarray which is already sorted. 

2) Remaining subarray which is unsorted. In every iteration of selection sort, the minimum element (considering ascending order) from the unsorted subarray is picked and moved to the sorted subarray.

 


We use the time.sleep() to make the operation to delay with the option of speed we set in the GUI. And also we use the displayArr function with every operations to practically visualize the sorting. We are using color yellow for this. For each bar : ["yellow" if x == j or x == j + 1 else "blue" for x in range(len(arr))]
This is how the selection sort works.

Next for the input ‘Bubble sort’. A Bubble sort is an easy algorithm among the various sorting algorithms. We learn it as a first sorting algorithm. It is easy to learn and highly intuitive. It can be easy to implement into the code, which is much beneficial for beginner software developers. But it is the worst algorithm for sorting the elements in every except because it checks every time the array is sorted or not. The bubble sort uses a straightforward logic that works by repeating swapping the adjacent elements if they are not in the right order. It compares one pair at a time and swaps if the first element is greater than the second element; otherwise, move further to the next pair of elements for comparison.

         



After every swap operation we use ["yellow" if x == j else "red" if x == j + 1 else "blue" for x in range(len(arr))] this particular color coding to see the changed in the sort canvas. 

Next up we have ‘Insertion Sort’. The Insertion sort is a straightforward and more efficient algorithm than the previous bubble sort algorithm. The insertion sort algorithm concept is based on the deck of the card where we sort the playing card according to a particular card. It has many advantages, but there are many efficient algorithms available in the data structure.

While the card-playing, we compare the hands of cards with each other. Most of the player likes to sort the card in the ascending order so they can quickly see which combinations they have at their disposal.

The insertion sort implementation is easy and simple because it's generally taught in the beginning programming lesson. It is an in-place and stable algorithm that is more beneficial for nearly-sorted or fewer elements.

The insertion sort algorithm is not so fast because of it uses nested loop for sort the elements.
                                      
The array spilled virtually in the two parts in the insertion sort - An unsorted part and sorted part.
The sorted part contains the first element of the array and other unsorted subpart contains the rest of the array. The first element in the unsorted array is compared to the sorted array so that we can place it into a proper sub-array.

It focuses on inserting the elements by moving all elements if the right-side value is smaller than the left side.
It will repeatedly happen until the all element is inserted at correct place.
To sort the array using insertion sort below is the algorithm of insertion sort.
•	Spilt a list in two parts - sorted and unsorted.
•	Iterate from arr[1] to arr[n] over the given array.
•	Compare the current element to the next element.
•	If the current element is smaller than the next element, compare to the element before, Move to the greater elements one position up to make space for the swapped element.
The color codes for the operations would be ["yellow" if x == j else "red" if x == j + 1 else "blue" for x in range(len(arr))]


All these functions are used in the GUI buttons which we will be using further. We create 2 combo boxes for algorithm and sort speed. And we create 2 buttons one for creating array and another one for sorting. This sort button will use the sort() function and the the create array button uses the createArr() function.
