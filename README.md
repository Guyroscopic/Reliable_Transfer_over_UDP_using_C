Specifications: 
This project creates a sender and receivers that implements video file transfer over UDP protocol using Linux/GNU C sockets. Sender is able to open a video file (or any file), read data chunks from file and write UDP segments, send these segments on UDP. Receiver must be able to receive, reorder and write data to a file at the receiving end.

Sender:
The sender works as follows: "Sender-filename listenport" (Command line Arguments)
The sender will read the file specified by the filename and transfer it using UDP sockets. On completing the transfer, the sender should terminate and exit. The sender binds to listenport to receive acknowledgments and other signaling from the receiver. Only a single UDP socket is used for both sending and receiving data.Note that although UDP will allow us to send large packets using IP fragmentation, but we make sure that we restrict our packets to 500 bytes (in payload)

Receiver:
The receiver should run as follows: "Receiver-filename listenport" (Command line Arguments)
The receiver binds to the UDP port specified on the command line and receive a file from the sender sent over the port. The file is saved to a different filename. Note that we should make sure in our testing that the filename used by the receiver is not the same as the one used by the sender. The receiver exits once the transfer is complete.

Implementing reliability in UDP:
We will implement the following to make UDP reliable:
a) Sequence numbers
b) Retransmission (selective repeat)
c) Window size of 5-10 UDP segments (stop n wait)
d) Re ordering on receiver side 
 
 
