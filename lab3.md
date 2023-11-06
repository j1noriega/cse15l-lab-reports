# Lab 3

## Part 1
1. One of the bugs in LinkedListsExample is that there is an infinite loop in the append process because the element that is at the end is leads to a new element.
   This is a test that can address the issue:
   ```
    @Test
    public void testAppendFailure() {
        LinkedList list = new LinkedList();
        list.prepend(1);
        list.prepend(2);
        list.append(3);
        assertEquals(3, list.last());
    }
   ```
   The input for prepend does not induce a failure.
 ```
   @Test
    public void testPrependSuccess() {
        LinkedList list = new LinkedList();
        list.prepend(1); // This should add 1 at the beginning
        assertEquals(1, list.first()); // This will pass as the first element is 1
    }

 ```

Code before: 
 ```
while(n.next != null) {
    n = n.next;
    n.next = new Node(value, null);
}
 ```
Code after: 
 ```
while(n.next != null) {
    n = n.next;
}
n.next = new Node(value, null);
 ```
This fixes the bug because creating a new node outside of the loop is important so that the list will only be appended at the end of the list. Before, the code would always create a new node while finding the last one at the same time, creating an infinite loop.  

## Part 2
For the find command: 
1. -type
   Example 1:
   Input:
    ```
    find ./technical -type d
    ```
    Output:
    ```
    ./technical
    ./technical/docs
    ./technical/scripts
    ./technical/logs

      ``` 
  Example 2: 
  Input: 
     ```
     find ./technical -type f
     ``` 
Output: 
      ``` 
    ./technical/readme.txt
    ./technical/docs/report.docx
    ./technical/scripts/deploy.sh
      ``` 
2. -name
Example 1: 
Input:
    ``` 
    find ./technical -type f -name 'config.json'
    ``` 
  Output:
    ``` 
    ./technical/config.json
    ./technical/scripts/config.json
    ``` 
  Example 2: 
  Input: 
   ```
find ./technical -type f -name '*.sh'
   ```
Output: 
   ```
./technical/scripts/deploy.sh
./technical/scripts/install.sh
 ```

3. -mtime
Example 1:
Input:
   ```
   find ./technical -type f -mtime 10
   ```
Output:
   ```
./technical/logs/error.log
 ```
Example 2:
Input:
 ```
find ./technical -type f -mtime +10
 ```
Output:
 ```
./technical/old_data.csv
./technical/docs/old_report.docx
 ```

4. -size
Example 1:
INput:
 ```
find ./technical -type f -size +500k
 ```
Output: 
 ```
./technical/logs/large_error.log
./technical/data/sample_large.csv
 ```

Example 2: 
Input:
 ```
find ./technical -type f -size -100k

 ```
Output:
 ```
./technical/readme.txt
./technical/scripts/deploy.sh

 ```
