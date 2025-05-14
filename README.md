# Module: 9 Publisher
**NPM:** 2306174135  
**Name:** Andhika Nayaka Arya Wibowo

**1. How much data does your publisher program send to the message broker in one run?**  
In each execution, the publisher sends **5 messages**. Each message is a Borsh-serialized `UserCreatedEventMessage` struct containing:
- `user_id` (String)
- `user_name` (String)

The exact byte size of each message depends on the length of those strings plus Borsh’s serialization overhead, so the total data sent equals the sum of the sizes of these five serialized messages.

---

**2. The URL “amqp://guest:guest@localhost:5672” is the same as in the subscriber program. What does it mean?**
- **Protocol:** AMQP
- **User/Password:** `guest` / `guest`
- **Host:** `localhost` (connects to RabbitMQ running locally)
- **Port:** `5672` (RabbitMQ’s default AMQP port)

Using the same URL in both publisher and subscriber ensures they connect to the **same** RabbitMQ broker instance with the same credentials.