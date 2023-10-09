## Lab 1

## 1. cd
   
  **No arguments:**

  ![Image](cd_no_argument.png)

  The working directory is /home when the command was run. "cd" does not have any arguments so it will just change the working directory to home. Therefore, pwd will demonstrate this change by giving /home as an output.  The output is not an error. 


**Command with a path to a directory as an argument:**

  ![Image](cd_directory_argument.png)

  The working directory was /home when the command was run. The output was /home/lecture1 because cd made lecture1 the working directory, which is under /home. The output is not an error. 

  **Command with a path to a file as an argument:**
  
  ![Image](cd_file_directory.png)
  
The working directory was /home when the command was run. I received this output because I used Hello.java as if it were a directory. Therefore, the output is an error because Hello.java is a file when cd expected a directory as an argument. 


## 2. ls

   **No arguments:**

   ![Image](ls_no_argument.png)

The working directory was /home/lecture1 when the command was run. I got this output because there are no arguments, therefore ls will list what is within the current working directory. The output is not an error. 

**Command with a path to a directory as an argument:**

  ![Image](ls_directory_argument.png)

  The working directory was /home when the command was run. I got this output because ls shows what is inside the lecture1 directory. The output is not an error.

 **Command with a path to a file as an argument:**

   ![Image](ls_file_directory.png)

The working directory was /home/lecture1 when the command was run. I got this output because ls will list the file inside the directory that was inputted as the argument. The output is not an error. 

## 3. cat
