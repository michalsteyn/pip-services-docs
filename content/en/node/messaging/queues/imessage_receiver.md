---
type: docs
title: "IMessageReceiver"
linkTitle: "IMessageReceiver"
gitUrl: "https://github.com/pip-services3-nodex/pip-services3-messaging-nodex"
description: >
  Callback interface to receive incoming messages.
---

### Description

The IMessageReceive interface is used to receive incoming messages. 

### Instance methods

#### receiveMessage
Receives an incoming message from the queue.

See also [MessageEnvelope](../message_envelope), [IMessageQueue](../imessage_queue)

> receiveMessage(envelope: [MessageEnvelope](../message_envelope), queue: [IMessageQueue](../imessage_queue)): Promise\<void\>

- **envelope**: [MessageEnvelope](../message_envelope) - incoming message
- **queue**: [IMessageQueue](../imessage_queue) - queue where the message comes from

### Examples

```typescript
class MyMessageReceiver implements IMessageReceiver {
  public async receiveMessage(envelop: MessageEnvelop, queue: IMessageQueue): Promise\<void\> {
      console.log("Received message: " + envelop.getMessageAsString());
  }
}

let messageQueue = new MemoryMessageQueue();
messageQueue.listen("123", new MyMessageReceiver());

await messageQueue.open("123")
await messageQueue.send("123", new MessageEnvelop(null, "mymessage", "ABC")); // Output in console: "ABC"
```
