
In **Yup**, a JavaScript schema validation library, you define **schemas** to validate objects. Each type (string, number, array, etc.) has its own set of **validation methods (aka keys or chains)**.

Here’s a categorized list of the most common **Yup validation keys**:

---

### 🔤 **String Schema**

```ts
yup.string()
```

|Key|Description|
|---|---|
|`required()`|Field must not be `undefined` or `null`|
|`min(length)`|Minimum length of the string|
|`max(length)`|Maximum length of the string|
|`email()`|Must be a valid email format|
|`matches(regex)`|Must match the regex|
|`url()`|Must be a valid URL|
|`uuid()`|Must be a valid UUID|
|`trim()`|Trim whitespace before validation|
|`lowercase()`|Transform to lowercase|
|`uppercase()`|Transform to uppercase|
|`oneOf([values])`|Must match one of the provided values|

---

### 🔢 **Number Schema**

```ts
yup.number()
```

|Key|Description|
|---|---|
|`required()`|Must be a number|
|`min(value)`|Minimum allowed number|
|`max(value)`|Maximum allowed number|
|`positive()`|Must be > 0|
|`negative()`|Must be < 0|
|`integer()`|Must be an integer|
|`lessThan(value)`|Must be < value|
|`moreThan(value)`|Must be > value|

---

### 🟢 **Boolean Schema**

```ts
yup.boolean()
```

|Key|Description|
|---|---|
|`required()`|Must be true or false|
|`oneOf([true])`|Often used for checkboxes|

---

### 🗂 **Array Schema**

```ts
yup.array()
```

|Key|Description|
|---|---|
|`of(schema)`|Schema for each array item|
|`min(length)`|Minimum number of items|
|`max(length)`|Maximum number of items|
|`required()`|Field must not be null or undefined|
|`length(length)`|Exact number of items|

---

### 🧱 **Object Schema**

```ts
yup.object()
```

|Key|Description|
|---|---|
|`shape({...})`|Define the structure of the object|
|`noUnknown()`|Disallow unknown keys|
|`required()`|Ensure it's not undefined/null|

---

### 🕹 **Mixed Schema** (Base type for all schemas)

```ts
yup.mixed()
```

|Key|Description|
|---|---|
|`required()`|Field is required|
|`nullable()`|Allow `null` values|
|`notRequired()`|Optional field|
|`oneOf([values])`|Must be one of the values|
|`test(name, message, fn)`|Custom validation logic|

---

### 🛠 Example

```ts
const schema = yup.object({
  name: yup.string().required().min(3),
  age: yup.number().required().min(18).max(60),
  email: yup.string().email(),
  isActive: yup.boolean().oneOf([true]),
  tags: yup.array().of(yup.string()).min(1),
});
```

Let me know if you want help building a validation schema for a specific form!