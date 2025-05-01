
```
import ChatModel from "../models/chatModel";

test("Initial test", () => {
  expect(2).toEqual(2);
});

describe("ChatModel", () => {

  it("should create a new chat document", () => {

    // Mock data for the chat document

    const mockChatData = {

      userId: "60d5f484f3a1c8b8f0e4e4f4",

      title: "Test Chat",

      createdAt: new Date(),

      updatedAt: new Date(),

    };

  

    // Create a new chat document using the model

    const chatDocument = new ChatModel(mockChatData);

    console.log(chatDocument);

  

    // Check if the document is an instance of the model

    expect(chatDocument instanceof ChatModel).toBe(true);

  

    expect(chatDocument.userId.toString()).toEqual(mockChatData.userId);

  

    expect(chatDocument.title).toEqual(mockChatData.title);

  });

  it("should have a timestatmp field", () => {

    const chatDocument = new ChatModel({

      userId: "60d5f484f3a1c8b8f0e4e4f4",

      title: "Test Chat",

    });

  

    // Check if the createdAt and updatedAt fields are present

    expect(chatDocument.createdAt).toBeDefined();

    expect(chatDocument.updatedAt).toBeDefined();

  });

});
```
this test case for 
```
import mongoose, { model, Schema } from "mongoose";
const chatSchema = new Schema(
  {
    userId: {
      type: mongoose.Types.ObjectId,
      ref: "User",
      required: true,
    },
    title: {
      type: String,
    },
    createdAt: {
      type: Date,
      default: Date.now,
    },
    updatedAt: {
      type: Date,
      default: Date.now,
    },
  },
  {
    timestamps: true,
  }
);
const ChatModel = model("chat", chatSchema);
export default ChatModel;
```

```
/ import { MongoMemoryServer } from "mongodb-memory-server";  
import mongoose from "mongoose";  
import UserModel from "../models/userModel";  
   
beforeAll(async () => {  
  await mongoose.connect("mongodb://localhost:27017/test-db-user");  
});  
   
afterAll(async () => {  
  await mongoose.connection.dropDatabase();  
  await mongoose.connection.close();  
});  
   
describe("User Model", () => {  
  it("Should create a new user", async () => {  
    const user = await UserModel.create({  
      username: "testuser",  
      password: "testpassword",  
      email: "test@mail.com",  
    });  
   
    expect(user._id).toBeDefined();  
    expect(user.username).toBe("testuser");  
    expect(user.password).toBe("testpassword");  
    expect(user.email).toBe("test@mail.com");  
  });  
   
  it("should retun error if username is not provided", async () => {  
    await expect(  
      UserModel.create({  
        password: "testpassword",  
        email: "test@mail.com",  
      })  
    ).rejects.toThrow();  
  });  
});
```