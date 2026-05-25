# 🐾 Runtime Polymorphism in Java

A beginner-friendly Java project demonstrating **Runtime Polymorphism** (Dynamic Method Dispatch) — one of the four core pillars of Object-Oriented Programming (OOP).

---

## 📌 What is Runtime Polymorphism?

**Runtime Polymorphism** occurs when a method call to an overridden method is resolved at **runtime** rather than at compile time.

In Java, this is achieved through:
- **Method Overriding** – A subclass provides its own implementation of a method defined in the parent class.
- **Parent Class Reference** – A reference variable of the parent class points to a child class object.
- **Dynamic Method Dispatch** – The JVM decides which method to call based on the actual object type at runtime.

> 💡 Key Rule: The method that gets called is determined by the **object type**, not the **reference type**.

---

## 📁 Project Structure

```
java-runtime-polymorphism/
│
├── Animal.java       # Base/Parent class
├── Dog.java          # Subclass 1 - overrides makeSound()
├── Cat.java          # Subclass 2 - overrides makeSound()
├── Cow.java          # Subclass 3 - overrides makeSound()
├── Main.java         # Entry point - demonstrates polymorphism
└── README.md
```

---

## 🧩 Class Overview

### `Animal.java` – Parent Class
Defines the base method `makeSound()` that all subclasses will override.

```java
class Animal {
    void makeSound() {
        System.out.println("Some animal makes a sound");
    }
}
```

---

### `Dog.java` – Subclass
Overrides `makeSound()` with dog-specific behavior.

```java
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Dog says: Woof!");
    }
}
```

---

### `Cat.java` – Subclass
Overrides `makeSound()` with cat-specific behavior.

```java
class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cat says: Meow!");
    }
}
```

---

### `Cow.java` – Subclass
Overrides `makeSound()` with cow-specific behavior.

```java
class Cow extends Animal {
    @Override
    void makeSound() {
        System.out.println("Cow says: Moo!");
    }
}
```

---

### `Main.java` – Entry Point
Demonstrates how a **parent class reference** calls different overridden methods at runtime.

```java
public class Main {
    public static void main(String[] args) {

        Animal myAnimal; // Parent class reference

        myAnimal = new Dog(); // Points to Dog object
        myAnimal.makeSound(); // Output: Dog says: Woof!

        myAnimal = new Cat(); // Points to Cat object
        myAnimal.makeSound(); // Output: Cat says: Meow!

        myAnimal = new Cow(); // Points to Cow object
        myAnimal.makeSound(); // Output: Cow says: Moo!
    }
}
```

---

## ▶️ Output

```
Dog says: Woof!
Cat says: Meow!
Cow says: Moo!
```

Even though `myAnimal` is of type `Animal`, the **actual object** at runtime determines which `makeSound()` is called. This is **Runtime Polymorphism** in action.

---

## ⚙️ How to Run

### Prerequisites
- Java Development Kit (JDK) 8 or above installed
- A terminal / command prompt

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/java-runtime-polymorphism.git
   cd java-runtime-polymorphism
   ```

2. **Compile all Java files**
   ```bash
   javac *.java
   ```

3. **Run the program**
   ```bash
   java Main
   ```

---

## 🧠 Concepts Covered

| Concept | Description |
|---|---|
| Inheritance | `Dog`, `Cat`, `Cow` extend `Animal` |
| Method Overriding | Subclasses provide their own `makeSound()` |
| Dynamic Method Dispatch | JVM resolves method call at runtime |
| Upcasting | Parent reference holds child object |

---

## 🆚 Compile-time vs Runtime Polymorphism

| Feature | Compile-time (Static) | Runtime (Dynamic) |
|---|---|---|
| Also called | Method Overloading | Method Overriding |
| Resolved at | Compile time | Runtime |
| Example | Same method name, different parameters | Parent reference, child object |

---

## 📚 Prerequisites to Understand This

Before exploring this project, it helps to know:
- Basic Java syntax
- Classes and Objects
- Inheritance (`extends` keyword)
- The `@Override` annotation

---

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Add more subclasses (e.g., `Bird`, `Lion`)
- Add a GUI version
- Extend with interfaces to show interface-based polymorphism

Fork the repo, make your changes, and open a pull request.

---



> ⭐ If this helped you understand runtime polymorphism, consider giving the repo a star!
