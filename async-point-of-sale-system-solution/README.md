# Async Point of Sale System

I built this restaurant ordering system using Python's `asyncio` for concurrent operations and real-time inventory management. It's designed to handle multiple orders simultaneously while maintaining accurate stock levels.

## 🍔 What I Built

- **Interactive Menu Display**: I created a system that lets you browse burgers, sides, and drinks with real-time pricing
- **Async Inventory Management**: I implemented real-time stock checking and updates that don't block the user interface
- **Combo Meal Creation**: I added automatic combo detection with a 15% discount when you order a burger, side, and drink together
- **Tax Calculation**: I included automatic 5% tax calculation on all orders
- **Stock Validation**: I made sure you can't order items that are out of stock
- **Multiple Order Support**: I designed it so you can place multiple orders in one session

## 📁 How I Structured the Project

```
async-point-of-sale-system-solution/
├── main.py          # I put the main application entry point here
├── inventory.py     # I handle inventory and catalogue management here
├── order.py         # I process orders and detect combos here
└── combo.py         # I manage combo meal logic and pricing here
```

## 🚀 Getting Started

### What You'll Need
- Python 3.7+ (I used asyncio features that require this version)
- No external dependencies (I kept it simple!)

### How to Run My Application

```bash
cd async-point-of-sale-system-solution
python main.py
```

## 🎯 How I Made It Work

### Menu Categories I Created
- **Burgers**: I included 6 different burger options (Python, C, Ruby, Go, C++, Java)
- **Sides**: I added Fries and Caesar Salad in multiple sizes
- **Drinks**: I included Coke, Ginger Ale, and Chocolate Milkshake in various sizes

### Async Operations I Implemented
- **Concurrent Stock Checking**: I made it so multiple items can be checked simultaneously
- **Thread-Safe Inventory**: I used asyncio.Lock for safe stock updates
- **Non-Blocking UI**: I ensured menu loading and order processing don't block your input

### Combo Detection I Built
I made the system automatically detect when you have:
- 1+ Burger
- 1+ Side  
- 1+ Drink

And I programmed it to create combo meals with a 15% discount.

## 💰 Pricing Example I Set Up

```
Python Burger: $5.99
Medium Fries: $3.49
Large Coke: $2.99
Subtotal: $12.47
Combo Discount: -$1.87
Tax (5%): $0.53
Total: $11.13
```

## 🔧 Technical Details I Implemented

### Key Classes I Built

#### `Inventory`
- I made it manage the product catalogue and stock levels
- I added async methods for stock checking and updates
- I implemented thread-safe operations with asyncio.Lock

#### `Order`
- I designed it to handle order creation and item addition
- I built automatic combo detection and pricing
- I added async item addition with stock validation

#### `Combo`
- I created it to represent a combo meal (burger + side + drink)
- I programmed it to apply 15% discount to combo items
- I made it handle combo string representation

### Async Features I Added
- `get_catalogue()`: I added a 2-second delay to simulate loading
- `get_stock()`: I included a 2-second delay for stock checking
- `decrement_stock()`: I made inventory updates atomic
- `add_item()`: I enabled concurrent item addition to orders

## 🎮 How to Use What I Built

1. **Start my application**: Run `python main.py`
2. **Browse the menu I created**: View available items and prices
3. **Add items**: Enter item numbers to add to your order
4. **Complete order**: Enter 'q' to finish ordering
5. **Review order**: I'll show you your items, combos, and total
6. **Purchase**: Confirm your order
7. **Repeat**: I give you the option to place another order

## 🛡️ Error Handling I Built

- I made sure invalid item numbers are rejected
- I programmed out-of-stock items to be automatically removed
- I added input validation for all your entries
- I included graceful handling of async operation failures

## 🔄 Order Flow I Designed

```
Load Catalogue → Display Menu → Add Items → Process Order → 
Check Stock → Create Combos → Calculate Total → Apply Tax → 
Display Summary → Confirm Purchase
```

## 📊 Performance Features I Optimized

- **Concurrent Operations**: I made multiple stock checks run simultaneously
- **Non-Blocking UI**: I ensured you can interact while async operations complete
- **Efficient Inventory**: I used O(1) item lookup with dictionary structure
- **Memory Efficient**: I minimized object creation during order processing

## 🎯 What I Learned Building This

This project taught me:
- Python asyncio programming
- Concurrent programming patterns
- Thread-safe data structures
- Object-oriented design
- Real-time inventory management
- User interface design
- Error handling in async contexts 
