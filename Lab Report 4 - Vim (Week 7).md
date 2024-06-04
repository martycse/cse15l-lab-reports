# <ins>Lab Report 4 - Vim (Week 7)</ins>
## Step 4

***<ins>Screenshot:</ins>***

<img width="669" alt="Screenshot 2024-05-21 at 10 18 06 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/57e6bb91-2de7-44bd-92a6-3371fad8cb86">

***<ins>Key Presses:</ins>***
* `control` + `shift` + [ ` ]
* `ssh` `map018@ieng6.ucsd.edu`
   * `<Enter>`

***<ins>Summary:</ins>*** *This part was pretty simple, I just opened a new `terminal` and logged into `IENG6` through the terminal using the `ssh` command and my id and then pressing `ENTER`. This resulted in a login displaying different information of the server and my server key.*

## Step 5

***<ins>Screenshot:</ins>***

<img width="868" alt="Screenshot 2024-05-21 at 10 42 34 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/240f1567-d9c5-4e79-8d18-07ee5271c8c7">

***<ins>Key Presses:</ins>***

* `<Command-C> --> git@github.com:martycse/lab7.git`

* `git clone` `<Command-V> --> git@github.com:martycse/lab7.git`

   * `<ENTER>`

***<ins>Summary:</ins>*** *This command used an `SSH fork link` and cloned it using the `git clone` command. This was done inside the `ssh` server which added the contents to the server.*


## Step 6

***<ins>Screenshot:</ins>***

<img width="1012" alt="Screenshot 2024-05-22 at 2 38 49 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/6ee43bfa-8572-4753-80f9-4c068a0a4875">


***<ins>Key Presses:</ins>***

* `cd lab7/` command
   - `<Enter>`
    
* `javac *.java` command
   - `<Enter>`
  
*`<up>` `<up>` `<up>` `<up>...........<up>` --> `bash test.sh` 
   * `<Enter>` 

***<ins>Summary:</ins>*** *To run the test I had forgotten the `bash test.sh` command so I used the `up` key several times (I had many commands in the history since the lab) to find it in the history and then hit `enter`. Before that I just typed `cd lab7/` then `enter`, then compiled with `javac *.java` then `enter` and then the previous command to run the tests. This was in order to head into the
correct directory, compile all files, and finally run the JUnit tests.*

## Step 7

***<ins>Screenshot:</ins>***

<img width="1011" alt="Screenshot 2024-05-22 at 2 52 24 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/d87c9142-1155-41b6-b1a4-92e6bcccd5e8">

<img width="432" alt="Screenshot 2024-05-22 at 2 52 50 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/787630a0-1c18-4abe-a019-ab8a6885a113">


***<ins>Key Presses:</ins>***
* `vim` `Test` `<TAB>` `Tests.java`
   * `<Enter>`
* `<:q!>`
* `vim` `Test` `<TAB>` `.java`
   * `<Enter>`
* `<:q!>`
* `vim` `Test` `<TAB>` `.java`
   * `<Enter>`
* In Vim: 6 key presses `<up>` then 11 key presses `<right>` then `<r>` `<2>` on the 1 character then `<:wq>`
   * `<Enter>` 

***<ins>Summary:</ins>*** *I typed `vim` then Test and used `tab` to fill in the rest and typed Tests in myself then I hit `enter` and realised I entered the wrong file. I exited using `:q!` to not save any changes in the file then I entered the other file TestExamples.java and edited some things wrong without realising so again I exited with `:q!`, then I re-entered and correctly edited in `vim` using the `arrow keys` as well as the `replace` shortcut to replace the 1 for a 2. Then I saved and exited vim using `:wq.` Entering vim allowed me to edit the tests within the terminal and edit
them quite easily with the replace tool as well as saving it too.*

## Step 8

***<ins>Screenshot:</ins>***

<img width="449" alt="Screenshot 2024-05-22 at 3 08 28 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/cdd015ce-aab8-4315-afa8-96af0a0e8a58">


***<ins>Key Presses:</ins>***

* `<up>` `<up>` `<up>` `<Enter>`

***<ins>Summary:</ins>*** *The 3 <up> key presses located the `bash test.sh` command and I simply clicked `enter` when I found it. This resulted in the tests running once more and showing they were now passing properly.*

## Step 9

***<ins>Screenshot:</ins>***

<img width="597" alt="Screenshot 2024-05-22 at 3 15 16 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/bd138d7e-1126-4640-bc10-0a2a4f5b7ec4">

***<ins>Key Presses:</ins>***

* `git add .` `<Enter>`
* `git commit -m "Fixed tests to work"` `<Enter>`
* `git push origin main` `<Enter>`

***<ins>Summary:</ins>*** *The `git add .` command stages all changed files. The `git commit -m` command allows me to commit the changes and add a message that can be a helpful description to what I changed.
Then the `git push origin main` command finally pushes the changes to the remote repo.*

