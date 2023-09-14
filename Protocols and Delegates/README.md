# Swift Protocols and Delegates README

## Introduction

This README provides a simple explanation of Swift protocols and delegates using a code example. In this example, we'll explore how to define protocols, implement them using classes and structs, and use delegates to delegate responsibilities.

## Table of Contents

- [What are Protocols?](#what-are-protocols)
- [What are Delegates?](#what-are-delegates)
- [Understanding the Code](#understanding-the-code)
- [How to Use the Code](#how-to-use-the-code)

## What are Protocols?

**Protocols** in Swift define a blueprint for methods, properties, and other requirements that a conforming class or struct must implement. Protocols are a way to define a set of behaviors without specifying how those behaviors should be implemented. They enable you to achieve polymorphism and create more flexible and reusable code.

In the code provided, we have defined a protocol named `AdvancedLifeSupport`:

```swift
protocol AdvancedLifeSupport {
    func performCPR()
}
```

This protocol declares that any conforming type must implement a method called `performCPR()`.

## What are Delegates?

**Delegates** in Swift are a design pattern that allows one object to delegate or hand off tasks to another object. Delegates are commonly used to define a contract between two objects, where one object (the delegate) agrees to perform certain tasks on behalf of another object. This helps in achieving separation of concerns and modularity in your code.

In the code, we have an `EmergencyCallHandler` class that has a `delegate` property of type `AdvancedLifeSupport`. This means that the `EmergencyCallHandler` can delegate the task of performing CPR to another object that conforms to the `AdvancedLifeSupport` protocol.

## Understanding the Code

Let's dive into the provided code to understand how protocols and delegates are used:

- We define the `AdvancedLifeSupport` protocol with a single method requirement: `func performCPR()`.

- The `EmergencyCallHandler` class has a `delegate` property of type `AdvancedLifeSupport`, which can be set to any object that conforms to the protocol.

- We create two classes, `Paramedic` and `Doctor`, both of which conform to the `AdvancedLifeSupport` protocol. These classes implement the `performCPR()` method differently, simulating how different types of medical professionals would perform CPR.

- The `Surgeon` class is a subclass of `Doctor` and overrides the `performCPR()` method to add a unique behavior.

- Instances of `Paramedic`, `Doctor`, and `Surgeon` are initialized and associated with an `EmergencyCallHandler` instance, effectively becoming the delegate for that handler.

## How to Use the Code

1. **Create an EmergencyCallHandler instance**:

   ```swift
   let emergencyCallHandler = EmergencyCallHandler()
   ```

2. **Initialize a medical professional as the delegate** (e.g., `Paramedic` or `Doctor`):

   ```swift
   let paramedic = Paramedic(handler: emergencyCallHandler)
   // or
   let doctor = Doctor(handler: emergencyCallHandler)
   ```

3. **Assess the situation**:

   ```swift
   emergencyCallHandler.assessSituation()
   ```

4. **Trigger a medical emergency**:

   ```swift
   emergencyCallHandler.medicalEmergency()
   ```

5. Observe the different behaviors of the delegate object when performing CPR based on the type of medical professional associated with the `EmergencyCallHandler`.

By following these steps, you can see how Swift protocols and delegates enable you to delegate responsibilities and achieve flexibility in your code, allowing different objects to respond to tasks in unique ways.

<p align="center">
  <samp>
    <a href="https://luuanfaria.dev">website</a> .
    <a href="https://linkedin.com/in/luuanfaria">linkedin</a> .
    <a href="https://twitter.com/luuanfariaf">twitter</a> .
  </samp>
</p>
