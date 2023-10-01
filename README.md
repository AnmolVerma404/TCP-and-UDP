# TCP and UDP

## Transmission Control Protocol (TCP)

### Pros

- It sends acknowledgement
- Guaranteed delivery
- Connection Based
- Congestion control
- Ordered Packets

### Cons

- Larger packets
- More bandwidth
- Slower than UDP
- Statefull
- Server memory (DOS)

### Code

- Go to `/TCP` run `npm i` to install all the dependencies
- Run `npm run start` to run the tcp server (Run the tcp server on a debugger if possible with line 6 as a breakpoint for better understanding)
- Install/Enable telnet in your OS
  - After installing follow these steps
  - Open a new terminal and write `telnet 127.0.0.1 8080`
  - This will send a tcp request from localhost i.e. 127.0.0.1 to 8080 port, and you will recieve `Hello` on telnet console
- Try to write on telnet terminal
  - If tcp server running on debugger, it will hit line 6 as data has been sent over, and show the data in debugger
- If you try to kill the server, the telnet will automatically lost the connection with no retained data. This is why TCP is stateful.

## User Datagram Protocol (UDP)

### Pros

- Smaller Packets
- Less bandwidth
- Faster than TCP
- Stateless

### Cons

- No Ack
- No guaranteed delivery
- Connectionless
- No Congestion control
- No ordered packets
- Security

### Code

- Go to `/UDP` and run `npm i` in your folder's terminal
- You need to install netcat on your os, best way is to do is linux
  - Just do `apt-get install netcat`, there are other way to install but they are quite lenghty
- Run your server (if possible run in debug mode and add a breakpoint on line 5)
- Go to your wsl terminal and run `echo "hi" | nc -w1 -u 127.0.0.1 8081`
  - Just `echo "hi"` will print "hi" in terminal but when added with "|" it pipes the logged "hi" to the netcat server with here is running on port 8081 from netcat port localhost.
