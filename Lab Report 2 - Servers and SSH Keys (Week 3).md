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

## `/add-message` Screenshot 1:
**`/add-message?s=Hello&user=Martin`**
<img width="1709" alt="Screenshot 2024-04-24 at 6 39 59 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/0bc17e97-ebd7-4605-9de2-f2c0a5240242">




