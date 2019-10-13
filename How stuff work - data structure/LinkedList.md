<h1>Linked List</h1><hr>

<pre>
-----------------------       -----------------------       -----------------------       -----------------------
| Value: 12           |-----\ | Value: 43553        |-----\ | Value: 746          |-----\ | Value: 2213         |
| Next_Address:056ffx |-----/ | Next_Address:078afx |-----/ | Next_Address:079abx |-----/ | Next_Address:NULL   |
-----------------------       -----------------------       -----------------------       -----------------------
</pre>
<p>In the above diagaram each box represents a <b>Node</b> , which refers to the preliminary entity of the <i>linked list</i>
data structure. Value represents the value held by the node and Next_Address refers to the address in memory space for fetching the next value on the linked list. </p>
<p><b>Advantages:</b><br/>
<ul type="disc">
  <li>Efficient for rigorous insertion and deletion operations
  <li>List can be resized during the run time.
  <li>Efficient memory allocation.
</ul>
</p>

<p><b>Disadvantages:</b><br/>
<ul type="disc">
  <li>Storing pointers takes up extra memory space.
  <li>Linked List must be traversed from starting till the end to search for an element.
  <li>Back traversal is quite complicated for singly-linked list, though doubly linked list is simpler for reverse traversal but takes up extra memory for backward pointer assosciated with each node.
</ul>

</p>

<p>
<h1><u>Algorithms</u></h1>
Consider temp as a user defined data-structure consisting of elements: value and next, head is of same datatype as temp and points towards the starting node of the linked list
<h5>Search</h5>
 <pre>
 find_element(head,element):
    temp=head
    while(temp is not None):
        if(temp.value==element):
            return index_of_element
        elif(temp is None):
            return "Not Found"
        temp=temp.next
 </pre>
 
 <h5>Insertion</h5>
 <pre>
 insert_into_linked_list(head):
    temp=head
    while(temp is not None):
      curr_val=temp.value
      temp=temp.next
 </pre>
 
 <h5>Deletion</h5>
 <pre>
 delete_from_linked_list(head,element):
    temp=head
    while(temp is not None):
      if(temp.next.value==element):
          temp.next=temp.next.next
          return "Element Deleted"
      elif(temp is None):
          return"Element not found"
      temp=temp.next
 </pre>
 
 <h2>Further Reading</h2>
 <ul type="disc">
  <li><a href="https://www.geeksforgeeks.org/data-structures/linked-list/">Geeks for Geeks</a>
  <li><a href="https://www.tutorialspoint.com/data_structures_algorithms/linked_list_algorithms.htm">Tutorials Point</a>
  <li><a href="https://www.hackerearth.com/practice/data-structures/linked-list/singly-linked-list/tutorial/">Hacker Earth</a>
  <li><a href="https://en.wikipedia.org/wiki/Linked_list">Wikipedia</a>
  <li><a href="https://www.hackerrank.com/domains/data-structures?filters%5Bsubdomains%5D%5B%5D=linked-lists">HackerRank</a>
 </ul>
