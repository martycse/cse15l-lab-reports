# Lab Report 2 - Servers and SSH Keys (Week 3)
## Part 1

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
        return "Invalid request"; // Default response
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
