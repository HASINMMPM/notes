### **Socket io**

- **Socket.io** is build in top of websocket
- web socket help real time bidimentional comminication ( There is no need for wait others or req ) between client and server.
    (there is no need for refresh or fetch)
- Example :- Chat app , multiplayer games, collaborative tools

```js
import express from "express";
import { createServer } from "node:http";
import { Server } from "socket.io";

const app = express();
const port = 3000;
const httpServer = createServer(app);
const io = new Server(httpServer, {
	cors: {
		origin: "http://localhost:5173",
		methods: ["GET", "POST"],
	},
});

io.on("connection", (socket) => {
	console.log("A user connected");
	socket.on("message", (msg) => {
		console.log("Message is:", msg);
		io.emit("message", msg);
	});
	socket.on("disconnect", () => {
		console.log("User disconnected");
	});
});
httpServer.listen(port, () => {
	console.log(`Server listening on port ${port}`);
});
```

if we enter in that origin it show **'A User connected'** and if close that tab it show **"User disconnected"**.

```jsx
import React, { useEffect, useState } from "react";
import { io } from "socket.io-client";
const socket = io("http://localhost:3000");

const ChatApp = () => {
	const [messages, setMessages] = useState([]);
	const [inputmsg, setInputMsg] = useState("");
	const handleSend = () => {
		if (inputmsg.trim().length > 0) {
			socket.emit("message", inputmsg);
			setInputMsg("");
		}
	};
	useEffect(() => {
		socket.on("message", (msg) => {
			setMessages((prev) => [...prev, msg]);
		});
		return () => {
			socket.off("message");
		};
	}, []);

	return (
		<div>
			      <h1>Chat App</h1>     {" "}
			<div className="flex flex-col gap-2">
				       {" "}
				{messages.length > 0 ? (
					messages.map((msg, i) => (
						<div key={i} className="bg-gray-200 p-2 rounded">
							              {msg}           {" "}
						</div>
					))
				) : (
					<div>No messages</div>
				)}
				        <div className="input mt-4">
					         {" "}
					<input
						className="border-2 border-black p-2"
						type="text"
						value={inputmsg}
						onChange={(e) => setInputMsg(e.target.value)}
					/>
					         {" "}
					<button
						className="ml-2 cursor-pointer bg-sky-300 p-2"
						onClick={handleSend}
					>
						            Send          {" "}
					</button>
					       {" "}
				</div>     {" "}
			</div>
			   {" "}
		</div>
	);
};
export default ChatApp;
```

- **full duplex** is like a call it continusly communicating
- It uses events to trigger actions and exchange data between the client and server.

---

##### Key Features of Socket.IO:

1. **Real-Time Bidirectional Communication:** Socket.IO enables instant communication between clients and servers, allowing for seamless updates and interactions in web applications.
2. **Automatic Reconnection:** Socket.IO automatically handles reconnection attempts in case of connection loss, ensuring reliable communication even in unstable network conditions.
3. **Multiplexing:** Socket.IO supports multiplexing, allowing multiple logical connections to be established over a single physical WebSocket connection. This improves efficiency and reduces overhead.
4. **Fallback Mechanisms:** Socket.IO provides fallback mechanisms, such as long polling, for environments where WebSocket connections are not supported or are unreliable.
5. **Room Support:** Socket.IO allows clients to join and leave named rooms, enabling targeted message broadcasting to specific groups of clients.

---

- Socket.IO uses event-based communication.
- The connection stays alive (persistent).
- Always secure your connections for production (e.g., with HTTPS and auth).
- Use `socket.id` to track individual clients.
- You can create "rooms" or "namespaces" for advanced use cases.
