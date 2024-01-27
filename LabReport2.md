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
Along with this code file I have used a Server.java file which defines the interface URLHandler, class ServerHttpHandler and class Server.

Brief Explanation of `ChatServer.java` code :
The `ChatServer.java` file contains 2 classes - the Handler class and the ChatServer class. The Handler class checks whether the URL contains the `\add-message` query. 
If this query is found then the string following is split to find the `user` and the `message`. Then, the string `<user> : <s> \n` is appended to the array `list` which keeps track of all the message strings. 

![Image](ChatServer2.png)

* All 3 methods in my code are called - handleRequest(), printingTheList() and main().
* Methods and Fields :
      The argument passed to the handleRequest method was `url` which is `URI("https://0-0-0-0-4002-9cal1u4bsa735bcuusnesev140.us.edusercontent.com/add-message?s=Hello&user=jpolitz")`.
      The argument to main() was args which is the port number. The port number passed for this case was 4002.
      Here the `List = ["jpolitz: Hello\n"]` and its `size=1`.
* Changes :
      The url passed to the handleRequest() method changes from null to `URI("https://0-0-0-0-4002-9cal1u4bsa735bcuusnesev140.us.edusercontent.com/add-message?s=Hello&user=jpolitz")`.
      The parameters array becomes `["s=Hello", "user="jpolitz"]`.
      The text array and user array also changes based on the .split() method.
      The field `chatmMessage` becomes `"jpolitz: Hello\n"`.
      Finally, the List changes from `[]` to `["jpolitz: Hello\n"]` and size changes from 0 to 1.

![Image](ChatServer1.png)

* All 3 methods in my code are called - handleRequest(), printingTheList() and main().
* Methods and Fields :
      The argument passed to the handleRequest method was `url` which is `URI("https://0-0-0-0-4002-9cal1u4bsa735bcuusnesev140.us.edusercontent.com/add-message?s=Hi&user=Ridhi")`.
      The argument to main() was args which is the port number. The port number passed for this case was 4002.
      Here the `List = ["Ridhi: Hi\n"]` and its `size=2`.

