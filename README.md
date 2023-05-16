# Reverse_Linked_List_Using_Java_8

package Com.nt.java8;

import java.util.LinkedList;

/**

 * We collect the elements of the input linked list the stream() method. we
 * 
 * collect the elements of the stream into a new linked list using the collect()
 * 
 * with argument. the first arguments is Supplier that creates a new LinkedList
 * 
 * object. The Second arguments is a BiConsumer thats add each element to the
 * 
 * Beginning of the linked list using the addFirst.
 * 
 * @author 2232829
 *
 */
public class ReverseLinkedList {

	public static void main(String[] args) {
  
		LinkedList<Integer> list = new LinkedList<>();
    
		list.add(1);
    
		list.add(3);
    
		list.add(15);
    
		list.add(2);
    
		list.add(5);
    
		list.add(20);
    
		System.out.println(list);

		LinkedList<Integer> reversedList = reverseList(list);
    
		System.out.println(reversedList);
    
	}

	public static <T> LinkedList<T> reverseList(LinkedList<T> list) {
  
		return list.stream().sorted().collect(LinkedList::new, LinkedList::addFirst, LinkedList::addAll);

	}

}

Output: 

[1, 3, 15, 2, 5, 20]

[20, 15, 5, 3, 2, 1]
