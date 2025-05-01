

-  **Centralized Logic**: Avoids repetitive error handling code across routes and controllers.
- **Consistent Responses**: Provides uniform error messages to clients.
- **Simplified Debugging**: Enables systematic logging of errors for easier troubleshooting

---

## 🧱 1. Express Server Setup

The article begins by setting up a basic Express server with TypeScript:

**`index.ts`** – Starts the server:

```ts
import app from "./app";

const initServer = async () => {
  app.listen(8000, () => {
    console.log(`Listening on port ${8000}`);
  });
};

initServer();
```

**`app.ts`** – Configures the Express application:

```ts
import express from "express";
import { json } from "body-parser";
import userRouter from "./routes/users";

const app = express();

app.use(json());
app.use(userRouter);

export default app;
```

---

## 📁 2. Routes and Simulated Data

A simple user route is set up with in-memory data and simulated asynchronous behavior:

**`routes/users.ts`**:

```ts
import { Request, Response, Router } from "express";

const router = Router();

const userData = [
  { id: 1, name: "Sam" },
  { id: 2, name: "Bob" },
  { id: 3, name: "Joe" },
];

const fetchUserData = (): Promise<typeof userData> => {
  return new Promise((resolve, reject) => {
    const randomNum = Math.floor(Math.random() * 10 + 1);
    setTimeout(() => {
      if (randomNum === 1) {
        reject("Error: Something went wrong!");
      } else {
        resolve(userData);
      }
    }, 1000);
  });
};

const getHandler = async (req: Request, res: Response) => {
  const { id } = req.query;
  if (!id) {
    return res.status(400).send({ message: "Id is required!" });
  }

  try {
    const fetchedUserData = await fetchUserData();
    const filteredUserData = fetchedUserData.filter(
      (user) => user.id === parseInt(id as string)
    );
    return res.status(200).send({ data: filteredUserData });
  } catch (err) {
    return res.status(500).send({ message: err });
  }
};

const postHandler = (req: Request, res: Response) => {
  const { name } = req.body;
  if (!name) {
    return res.status(400).send({ message: "Name is required!" });
  }

  const newUser = {
    id: userData.length + 1,
    name,
  };

  userData.push(newUser);
  return res.status(201).send({ data: newUser });
};

router.get("/users", getHandler);
router.post("/users", postHandler);

export default router;
```

---

## 🧠 3. Error Handling Strategy

The article emphasizes the importance of structured error handling in Express applications. Key practices include:

- **Centralized Error Handling**: Implementing a global error handler middleware to catch and process errors uniformly.
    
- **Custom Error Classes**: Creating custom error classes to represent different error types, allowing for more precise error management.
    
- **Environment-Based Responses**: Differentiating error responses based on the environment (development or production) to avoid exposing sensitive information.
    

---

## 🛠️ 4. Implementing a Global Error Handler

While the article sets the stage for implementing a global error handler, the specific code for the middleware isn't provided in the excerpt. However, a typical error handler in Express with TypeScript might look like this:

```ts
import { Request, Response, NextFunction } from "express";

export const errorHandler = (
  err: any,
  req: Request,
  res: Response,
  next: NextFunction
) => {
  const statusCode = err.statusCode || 500;
  const message = err.message || "Internal Server Error";

  const response: any = {
    message,
  };

  if (process.env.NODE_ENV === "development") {
    response.stack = err.stack;
  }

  res.status(statusCode).json(response);
};
```

This middleware captures errors, assigns appropriate status codes and messages, and conditionally includes stack traces based on the environment.

---

## 📌 Conclusion

The article provides a foundational approach to error handling in Express applications using TypeScript. It underscores the significance of:

- Establishing a centralized error handling mechanism.
    
- Utilizing custom error classes for clarity and specificity.
    
- Tailoring error responses to the application's environment.
    

For a comprehensive understanding and additional code examples, you can read the full article here: [Express Error Handling Like a Pro using TypeScript](https://medium.com/@xiaominghu19922/proper-error-handling-in-express-server-with-typescript-8cd4ffb67188).


try catch le try le error throw cheythal ath catch le ethum then avdenn next call cheythal error handler le ethum