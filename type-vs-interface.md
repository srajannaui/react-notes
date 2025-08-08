# Type vs Interface in TypeScript

When working with TypeScript, both `type` and `interface` can be used to define object shapes. However, they serve slightly different purposes and have unique strengths.

---

## ✅ When to Use `interface`

- Extending other interfaces (`extends`)
- Creating component props (commonly used in React)
- Implementing with classes
- When declaration merging is helpful (especially in libraries)

```ts
interface User {
  name: string;
  email: string;
}

interface Admin extends User {
  isAdmin: boolean;
}
```

---

## ✅ When to Use `type`

- Union and intersection types
- Aliasing primitives, arrays, functions, or tuples
- Conditional or mapped types
- When combining multiple complex types

```ts
type Theme = 'light' | 'dark';
type UserOrNull = User | null;
type Callback = (data: string) => void;
type UserWithTheme = User & { theme: Theme };dmin: boolean;
```

---

🧠 Feature Comparison
| Feature                 | `interface` | `type`         |
| ----------------------- | ----------- | -------------- |
| Object shape definition | ✅           | ✅              |
| Extendability           | ✅ `extends` | ✅ `&` operator |
| Declaration merging     | ✅           | ❌              |
| Union types             | ❌           | ✅              |
| Tuples / functions      | ❌           | ✅              |
| React component props   | ✅           | ✅              |
| Implements in classes   | ✅           | ❌              |

---

✅ Summary

Use interface for extendable and mergeable structures (like props, class models).

Use type for unions, intersections, and flexible compositions.

Prefer consistency in your codebase or follow your team’s standard.