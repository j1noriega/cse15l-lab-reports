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
    This command lists all the directories within the ./technical directory. This is useful when you want to focus on directory structures.
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
   This command lists all the regular files within the ./technical directory. This can be very useful when you want to perform actions on just the files and not directories.


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
    This command searches for all files named config.json in the ./technical directory and subdirectories. This is useful when you need to locate files with a specific name.
    
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
This command searches for files that have a .sh extension, which usually denotes shell scripts. It’s helpful when you need to find script files.

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
This command lists files that were last modified exactly 10 days ago. It’s useful for locating files that changed on a specific date.

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
This command lists files modified more than 10 days ago. This can be used for cleanup or archiving older files.

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
This command finds files larger than 500KB. This is useful for locating files that may be taking up too much space. 

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
This command finds files that are smaller than 100KB. This could be useful when you are searching for small configuration or property files.
