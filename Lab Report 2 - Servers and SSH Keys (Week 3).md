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

        // Assuming Server.start() is a method that starts a server and takes a port and a handler
        Server.start(port, new Handler());
    }
    
}
```
## Code (Screenshot of workspace)
<img width="1710" alt="Screenshot 2024-04-24 at 8 36 13 PM" src="https://github.com/martycse/cse15l-lab-reports/assets/146497948/5fce9227-8101-48ed-9392-c4bbf5ef75e8">

