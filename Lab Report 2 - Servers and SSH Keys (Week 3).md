# Lab Report 2 - Servers and SSH Keys (Week 3)
# Part 1
## Code (written)

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String chat = "";
    
    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Chat Started!");
        } else if (url.getPath().equals("/add-message")) {
            String query = url.getQuery();
            if (query != null) {
                String[] params = query.split("&");
                String user = null;
                String message = null;
                for (String param : params) {
                    String[] pair = param.split("=");
                    if (pair.length == 2) {
                        if (pair[0].equals("user")) {
                            user = pair[1];
                        } else if (pair[0].equals("s")) {
                            message = pair[1];
                        }
                    }
                }
                if (user != null && message != null) {
                    chat += user + ": " + message + "\n";
                    return chat;
                }
            }
        }
        return "Error 404: Not Found!";
    }
}

class ChatServer{
    public static void main(String[] args) throws IOException {
        if (args.length == 0) {
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }
        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
    
}
```
## Code (Screenshot of workspace)
<img width="1710" alt="Screenshot 2024-04-24 at 8 41 34 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/7b7cf605-3ebc-4fc2-b3d4-e14dc77a9706">

## `/add-message` Screenshot 1, Example 1:
**The first example below is using: `/add-message?s=Hello&user=Martin`**
<img width="1709" alt="Screenshot 2024-04-24 at 6 39 59 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/0bc17e97-ebd7-4605-9de2-f2c0a5240242">
**Questions and Answers**
* Question 1: Which methods in your code are called?
1. *The methods that are called from my code are; the `handleRequest` method which is located in `ChatServer.java` under the `Handler class` as well as the getPath and getQuery methods which are implemented from URLHandler. Additionally, the `handle` method is used under the `ServerHttpHandler class` which is located in `Server.java.`*
* Question 2: What are the relevant arguments to those methods, and the values of any relevant fields of the class?
2. *The relevant arguments to the `handleRequest` method include the `URI url` argument which is the url itself for the web page which is in the `Handler` class. Then, its relevant fields and arguments within the class include `String user`, `String message`,`String chat`,`query`, `URI url` and `params`.*
* Question 3: How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
3. *The `user value` takes the value of the second `query` which in this case is `Martin` and the `message value` takes in the first `query` which in this case is `Hello!!!`. The params variable is able to identify where multiple query parameters are and splits them to use within the same process. Then at the end, the `chat` field changes with this url path request and becomes "Martin: Hello!!!". In addition, the `URI url` is the `/add-message?s=Hello!!!&user=Martin`.*

## `/add-message` Screenshot 2, Example 2:
**The second example below is using: `/add-message?s=How are you&user=Yoshi`**
<img width="1709" alt="Screenshot 2024-04-24 at 6 39 22 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/a04e77bf-a5e9-449a-bb36-7652530bf88d">
* Question 1: Which methods in your code are called?
1. *Again, the methods that are called from my code are; the `handleRequest` method which is located in `ChatServer.java` under the `Handler class` and the `handle` method under the `ServerHttpHandler class` which is located in `Server.java`*
* Question 2: What are the relevant arguments to those methods, and the values of any relevant fields of the class?
2. *Again, the relevant arguments to the `handleRequest` method include the `URI url` argument which is the url itself for the web page which is in the `Handler` class. Then, its relevant fields and arguments within the class include `String user`, `String message`,`String chat`,`query`, `URI url` and `params`.*
* Question 3: How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
3. *The `user value` takes the value of the second `query` which in this case is `Yoshi` and the `message value` takes in the first `query` which in this case is `How are you?`. The params variable is able to identify where multiple query parameters are and splits them to use within the same process. Then at the end, the `chat` field changes with this url path request and becomes "Yoshi: How are you?". With this, the \n is used to create this message under the previous message "Martin: Hello!!!". In addition, the `URI url` is the `/add-message?s=How are you?&user=Yoshi`.*

# Part 2
## `ls` With the Absolute Path to the Private Key
<img width="1710" alt="Screenshot 2024-04-24 at 10 21 05 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/65a33f95-f384-42fd-adf4-be8df1582b94">

## `ls` With the Absolute Path to the Public Key
<img width="1710" alt="Screenshot 2024-04-24 at 11 02 38 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/7d957dd6-08bb-4e7b-a989-576014200e24">


## Logging in without a password
<img width="1710" alt="Screenshot 2024-04-24 at 10 29 44 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/ea3939be-eda6-4485-8472-eb2ac9a2cd40">

# Part 3
## Something I Learned:
***Something I learned during the Week 2 lab was that I could create and host local servers on a browser by using code in vscode and running it in the terminal with a port. It was really interesting to be able to learn that I can change the page and variables by using certain querys to the url and basically running the code through it. I really enjoyed learning this and it was also interesting to learn that it was possible to do this while still in the vscode terminal by using curl.***


