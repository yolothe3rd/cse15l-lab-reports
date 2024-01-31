### Lab Report 2 - Servers and SSH Keys (Week 3)

#### Part 1 
`ChatServer.java`:
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String str = "";
    int num = 0;
    public String handleRequest(URI url){
        if(url.getPath().equals("/")){
            return(String.format("%s", str));
        }
        else if(url.getPath().contains("/add")){
                String[] parameters = url.getQuery().split("=");
                if(parameters[1].length() < 6 || parameters.length == 2){
                    return "400 Bad Request";
                }
                String user = parameters[2];
                String msg = parameters[1].split("&")[0];
                if(num == 0){
                    str = String.format("%s: %s", user, msg);
                    num++;
                }
                else{
                    str = String.format("%s \n%s: %s", str, user, msg);
                }
                return(String.format("%s", str));
            }
        else{
            return(String.format("String: %s 1", str));
        }
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
