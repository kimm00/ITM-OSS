# Part 1: Dealing with git

1. **List all the branches in this repository and, for each branch, list the commits.**
   
    - git branch
      
<img width="388" alt="스크린샷 2024-10-12 오후 10 52 46" src="https://github.com/user-attachments/assets/50c46643-fd11-4e62-92c2-329a05ffaddb">

    - git checkout
      
<img width="473" alt="스크린샷 2024-10-12 오후 11 05 55" src="https://github.com/user-attachments/assets/36f7134d-4367-4df9-ad52-c6e0b575bce6">

    - git log --decorate
    
<img width="554" alt="스크린샷 2024-10-12 오후 11 06 05" src="https://github.com/user-attachments/assets/32956564-2acd-4708-a419-4543ff58b850">



   
2. **Try git log --graph --all to see the commit tree. Paste the result here and write a paragraph to provide an interpretation of what you found.**
    - git log --graph --all
      
  <img width="558" alt="스크린샷 2024-10-12 오후 11 13 54" src="https://github.com/user-attachments/assets/eb43562d-50a9-4960-aa60-f6a70781387f">

  1) master branch (HEAD -> master)
: commit c146e374cd120f91c18ee97679cdb148d9bde6e9 / This commit means "Adding class B skeleton and Main class", the author is Josue Obregon, and he committed this on 19 August in 2024. (After all of commits were commited by Josue Obregon.)
  2) feature-msg branch (feature-msg)
: commit 71bcd3fc4b13ba0d4df2270259392a75025fdfa9 / This commit is made by feature-msg. This means "Adding header of method printMessage()".
  3) previous commits
: commit b487ec97a3f8626bf4b427df5bc73f00d334c7b9 / This commit "Adding class A skeleton." -> Commit with skeleton for class A
: commit f6f58b7977bddf977c0fcc880113ef27a5740a8f / This commit is the initial of the repository, a commit created empty for all files. 





3. **Choose an already existing branch and use git diff BRANCH_NAME to view the differences between a branch and the current branch. Summarize the difference from master to the other branch.**
    - git diff fearue-msg
      
   <img width="531" alt="스크린샷 2024-10-12 오후 11 24 23" src="https://github.com/user-attachments/assets/00bf8968-8c32-495c-ab69-28f78b8f480d">

Differneces between master branch and feature-msg branch

  1) A.java
: master: printMessage() method is empty.
: featue-msg: printMessage() method is deleted.
  2) B.java
: newly added in feature-msg which is not existed in master.
: class B has been added, but it only has skeleton with no content exits.
  3) Main.java
: feature-msg is newly added which is not existed in master.
: Main class and main() method has been added with no functioning.





4. **Write a command sequence to merge the branch that is not the master branch into master.**
    1) Switch to the master branch
       - git checkout master
    2) Merge the feature-msg branch into master
       - git merge feature-msg
    3) Resolve the conflicts
       - nano A.java
       - erase all the factors that make errors (ex. <<<<<, ====, >>>>)
    4) git add A.java
    5) git commit
    6) Check the merge is successful
       - git log --online --graph
         
  <img width="489" alt="스크린샷 2024-10-12 오후 11 44 22" src="https://github.com/user-attachments/assets/b14ec50c-6285-4ebe-995d-97565e7c2666">
      
       -> Indicates that feature-msg branch has merged into the master brnach. The two branches have now merged into one. 






5. **Write a command (or sequence) to (i) create a new branch called print-msg (from the master) and (ii) change to this branch.**
    - Make new branch named print-msg in master brnach
      : git checkout -b pring-msg master
      
<img width="532" alt="스크린샷 2024-10-12 오후 11 48 07" src="https://github.com/user-attachments/assets/7ab85256-f19b-4eb1-89a7-fd3eff1776e3">






6. **Edit A.java adding the following implementation code for the printMessage() method.**
    ```java
    System.out.println("This is a new message.");
    System.out.println("Git is fun, isn't it?");
    ```

  - Open A.java
    : nano A.java
  - Edit A.java
    
<img width="568" alt="스크린샷 2024-10-12 오후 11 50 13" src="https://github.com/user-attachments/assets/c56f9da9-bd45-4de7-acdc-408c014ebaf8">


    

7. **Write a command (or sequence) to commit your changes.**
    1) Adding a changed file to git
      : git add A.java
    2) Commit the changes
      : git commit -m "Implement printMessage method in A.java"

<img width="564" alt="스크린샷 2024-10-12 오후 11 54 01" src="https://github.com/user-attachments/assets/3af1d8f1-c6ee-4bc2-8c09-52cdcbc2b5a4">






8. **Change back to the master branch and change A.java adding the following implementation code for the printMessage() method (commit your change to master):**
    ```java
    System.out.println("Hello opensource world!");
    ```

    1) Switched to branch 'master'
       : git checkout master
    2) Open A.java
       : nano A.java
    3) Modify A.java
       
<img width="562" alt="스크린샷 2024-10-12 오후 11 57 43" src="https://github.com/user-attachments/assets/55d8a8dd-7622-4d24-a3e1-31bd1774d0e4">
   
    4) Add a changing file to git
       : git add A.java
    5) Commit changes to master branch
       : git commit -m "Add 'Hello opensource world!' to printMessage method in A.java"
       
<img width="566" alt="스크린샷 2024-10-12 오후 11 59 12" src="https://github.com/user-attachments/assets/e7b11926-f6b4-44dc-88c8-d9be20e1b381">






9. **Write a command sequence to merge the print-msg branch into master and describe what happened.**
   1) Convert into master branch
      : git checkout master
      - Already on 'master'
   2) Merge the print-msg branch
        * Erase the conflits
      -> I opened A.java and saw some conflicting markers, '<<<<<< HEAD, =====, >>>>>> print-msg') so I erased them.

<img width="524" alt="스크린샷 2024-10-13 오전 12 50 35" src="https://github.com/user-attachments/assets/27188073-791c-465a-9219-5e1d5c89f265">


     : git add A.java
     -> After solving the conflict, I saved the file and added it to the staging area. 
     : git commit
     -> I committed the merge to complete the process 
     
<img width="535" alt="스크린샷 2024-10-13 오전 12 04 11" src="https://github.com/user-attachments/assets/37c52977-243b-49ee-8ca8-1357060fa236">
       
       * Check the merge
    : git log --oneline --graph
    -> The merge was successfully completed, and both branches' changes were combined into the master branch. The print-msg branch changed, including the new printMessage() method: "Hello opensource world!" 
    
 <img width="543" alt="스크린샷 2024-10-13 오전 12 05 21" src="https://github.com/user-attachments/assets/44fd3cb5-826a-484e-8e99-5330316970e3">




10. **Write a set of commands to abort the merge.**
    1) Abort the merge
       : git merge --abort
    2) Check the situation
       : git status
       
    <img width="467" alt="스크린샷 2024-10-13 오전 12 11 29" src="https://github.com/user-attachments/assets/b719534e-30a4-4180-8be4-67ee8a592ee6">

-> This code means the merge has already been completed and there are no changes to commit. 

   



11. **Now repeat item 9, but proceed with the manual merge (editing A.java). All implemented methods are needed. Explain your procedure.**
    
    1) Switch to master branch
       : git checkout master
    2) Merge the print-msg branch
       : git merge print-msg

    * Conflicts occured
      - In print-msg branch
        : nano A.java

      public class A {
    public void printMessage() {
        System.out.println("Hello opensource world!");
        System.out.println("This is a new message.");
        System.out.println("Git is fun, isn't it?");
    }
}

     -> This procedure shows manually resolve the merging process and explain the procedure for maintaining all the methods. The important point is to manually resolve the conflict, remove the collision marker, and integrate the codes of the two branches to create the final code.
    
    3) Add the resolved file and complete the merge
       : git add A.java
    4) Complete the merge
       : git commit
    5) Merge again
       : git merge print-msg 
    6) Check the current situation 
       : git status
       -> nothing to commit, working tree clean



    

12. **Write a command (or set of commands) to proceed with the merge and make master branch up-to-date.**
    1) After solving conflicts, commit the merge
       - git add A.java : add file that conflicts were solved.
       - git commit : commit the merge
    2) Convert into master branch
       - git checkout master
    3) Merge print-msg to master; the content that solved in print-msg
       - git merge print-msg
    4) If the merge is completed, master branch is up to date, the same as the print-msg branch.
       - git log --online --graph
           -> We can identify if the merge is completed normally and master branch is latest stauts.  
      
   



13. **Complete Part 2. Then, come back here and answer the following: Report your experience of submitting the Part 2. Please, include the steps you followed, the commands you used, and the problems you faced (within the file you created for the Part 1).**
    - _답변을 여기에 입력하세요_
   






