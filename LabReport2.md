# Lab Report 2 

# Part One - Creating a Chat Server

Using java I have created a simple chat server which takes a query in the form `/add-message?s=<string>&user=<string>` and adds a chat message in the form `<user>: <message>`.

This is the `ChatServer.java` code : 

```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    int num = 0;
    String[] list = new String[10];
    int size = 0;

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return printingTheList();   
        } else if (url.getPath().contains("/add-message")) {
                String[] parameters = url.getQuery().split("&");
                String[] text = parameters[0].split("=");
                String[] user = parameters[1].split("=");
                if(size == list.length){
                        String[] list2 = new String[size*2];
                        for(int i=0; i<size; i++){
                            list2[i] = list[i];
                        }
                        list = list2;
                    }
                String chatMessage = user[1] + ": " + text[1] + "\n";
                list[size] = chatMessage;
                size += 1;
                return printingTheList();

        }
        return "404 Not Found!";
    }

    public String printingTheList(){
        String listString = "";
        for(int i=0; i<size; i++){
            listString += this.list[i];
        }
        return listString;
    }
}

class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```


