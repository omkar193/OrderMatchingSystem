# README

## **Order Matching System**

### **Overview**
This program simulates an order matching system designed to handle Buy Limit (BL) orders for financial securities. It processes incoming orders and matches them with real-time market prices (ticks). When a tick's price satisfies the conditions of an order, the order is executed, and the result is displayed.

### **Features**
1. **Order Management**:
   - Add new Buy Limit orders with a symbol, price, and quantity.
   - Assigns unique IDs to each order for tracking.

2. **Tick Processing**:
   - Handles real-time tick data (symbol, price, timestamp).
   - Matches ticks against pending orders based on price conditions.
   - Executes matching orders and removes them from the queue.

3. **Execution Logging**:
   - Displays details of executed orders, including order ID, execution time, price, and quantity.

---

### **Code Structure**
- **Order**: Represents a single Buy Limit order.
- **Tick**: Represents a market tick (price update).
- **OrderBook**: Core class that manages orders and processes ticks.
  - **addOrder**: Adds new orders to the system.
  - **newTick**: Adds ticks and processes matching orders.
  - **processTick**: Matches orders against tick prices and executes eligible orders.

---

### **How to Compile and Run**
1. Save the code to a file, e.g., `order_matching.cpp`.
2. Open a terminal and navigate to the file's directory.
3. Compile the code using:
   ```bash
   g++ -o order_matching order_matching.cpp
   ```
4. Run the compiled program:
   ```bash
   ./order_matching
   ```

---

### **Input and Output**

#### **Input**:
The program is pre-configured with:
1. **Orders**:
   - Example:
     ```plaintext
     AAPL, Buy Limit, Price: 100, Quantity: 10
     ```
2. **Ticks**:
   - Example:
     ```plaintext
     AAPL, Time: 09:00, Price: 104
     ```

#### **Output**:
When a tick matches an order:
```plaintext
Order 2 executed at 09:00, Price: 104, Quantity: 5
Order 3 executed at 09:01, Price: 102, Quantity: 15
```

---

### **Example Scenario**
#### **Orders**:
```plaintext
Order 1: AAPL, Buy Limit, Price: 100, Quantity: 10
Order 2: AAPL, Buy Limit, Price: 105, Quantity: 5
Order 3: AAPL, Buy Limit, Price: 102, Quantity: 15
```

#### **Ticks**:
```plaintext
[AAPL, Time: 09:00, Price: 104]
[AAPL, Time: 09:01, Price: 102]
```

#### **Output**:
```plaintext
Order 2 executed at 09:00, Price: 104, Quantity: 5
Order 3 executed at 09:01, Price: 102, Quantity: 15
```

---

### **Customization**
- Add more orders using `addOrder` in the `main` function.
- Simulate new market ticks using `newTick`.

---

### **Dependencies**
- **C++ Standard Library**:
  - `#include <iostream>`: For input/output.
  - `#include <vector>`: For managing collections.
  - `#include <map>`: For symbol-to-order mapping.
  - `#include <queue>`: For priority-based order processing.
  - `#include <string>`: For managing string data.

---

### **Algorithmic Details**
1. **Order Storage**:
   - Orders are stored in a `map` with symbols as keys and priority queues as values.
   - Priority queues prioritize orders with the lowest price (min-heap).

2. **Tick Processing**:
   - For each tick, match it against pending orders in the priority queue.
   - If the tick price satisfies the order condition, execute the order.

3. **Efficiency**:
   - The `map` allows O(1) access to orders for a symbol.
   - Priority queues provide O(log n) insertion and deletion, ensuring quick order matching.

---

### **Contact**
For questions or feedback, please reach out to:
**Name**: Omkar Kumar  
**Email**: omkarkumar193@gmail.com
