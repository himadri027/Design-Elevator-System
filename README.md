# 🚀 Elevator System (LLD) 🏢🔼🔽

Welcome to the **Elevator System Low-Level Design** — a multi-threaded, scalable simulation of real-world elevator mechanics. Built with extensibility, concurrency safety, and object-oriented elegance. 💡🛠️

---

## 📜 Problem Statement

Design and implement an **Elevator System** that:

- 🏙️ Handles **multiple elevators**
- 📥 Accepts and manages **floor requests**
- 🔄 Manages direction and state transitions
- ⚙️ Ensures **efficient request processing**

---

## 🧠 Features & Requirements

| Feature              | Description                                                  |
|----------------------|--------------------------------------------------------------|
| 🛗 Multiple Elevators | Manages more than one elevator concurrently                  |
| 🧍 Request Handling   | Supports user requests to move UP or DOWN                    |
| 🔼 Direction Control  | Tracks each elevator’s direction: UP, DOWN, or IDLE          |
| 🧭 State Management   | Maintains floor, moving status, and requests                 |
| ⏱️ Efficient Movement | Processes same-direction requests before switching directions |
| 🧩 Extensible         | Easily add elevators, algorithms, or features                |

---

## 🧱 Core Entities

### 1️⃣ Elevator

Represents a single elevator unit.

**Fields**:
- 🏢 `currentFloor` — Current floor location
- 🔄 `direction` — UP / DOWN / IDLE
- 📋 `pendingRequests` — Queue of floors to stop at
- 🚪 `isMoving` — Whether the elevator is in motion

**Key Methods**:
- `addRequest(Request request)`
- `move()`
- `openDoor()`, `closeDoor()`
- `processNextRequest()`
- `getCurrentFloor()`, `getDirection()`

---

### 2️⃣ ElevatorController

Coordinates all elevators and incoming user requests.

**Fields**:
- 📦 Holds one or more elevators

**Key Methods**:
- `requestElevator(int floor, Direction direction)`
- `step()` – Simulates elevator time step

---

### 3️⃣ Request

Encapsulates a single user request:

- 🔢 `floor` — Requested floor
- 📈 `direction` — Desired direction (UP/DOWN)

---

### 4️⃣ Direction (enum)

Enum values:  
```java
UP, DOWN, IDLE
