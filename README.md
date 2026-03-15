# 🛒 minimarket-api

A simple REST API mock data source for a minimarket/supermarket application. Contains a structured JSON dataset with 100 products ready to use in any frontend or backend project.

## 📦 Dataset Overview

The `products.json` file contains 100 supermarket products across 15 categories.

### Product Schema

```json
{
  "id": "p001",
  "name": "Red Apple",
  "category": "Fruits & Vegetables",
  "priceCents": 149,
  "stock": 200,
  "imageUrl": "https://images.unsplash.com/..."
}
```

| Field        | Type   | Description                              |
|--------------|--------|------------------------------------------|
| `id`         | string | Unique identifier (format: `p001`)       |
| `name`       | string | Product name                             |
| `category`   | string | Product category (in English)            |
| `priceCents` | number | Price in cents (e.g. 149 = $1.49)        |
| `stock`      | number | Available units in stock                 |
| `imageUrl`   | string | Product image URL from Unsplash          |

### Categories

| Category              | Products |
|-----------------------|----------|
| Fruits & Vegetables   | 13       |
| Dairy & Eggs          | 8        |
| Meat & Seafood        | 6        |
| Bakery                | 6        |
| Beverages             | 8        |
| Snacks                | 8        |
| Canned Goods          | 7        |
| Grains & Pasta        | 6        |
| Oils & Condiments     | 6        |
| Frozen Foods          | 6        |
| Cleaning Supplies     | 5        |
| Personal Care         | 6        |
| Spreads & Jams        | 4        |
| Breakfast & Cereals   | 4        |
| Spices & Seasonings   | 5        |

## 🚀 Usage

### As a static JSON API (with json-server)

```bash
# Install json-server
npm install -g json-server

# Start the mock API
json-server --watch products.json --port 3000
```

Your endpoints will be available at:

```
GET    http://localhost:3000/products         → All products
GET    http://localhost:3000/products/p001    → Single product
GET    http://localhost:3000/products?category=Beverages  → Filter by category
```

### Fetch in JavaScript

```js
const response = await fetch('http://localhost:3000/products');
const { products } = await response.json();
console.log(products);
```

### Import directly in a project

```js
import data from './products.json';
const { products } = data;
```

## 📁 Project Structure

```
minimarket-api/
├── products.json   # Main dataset (100 products)
└── README.md       # Documentation
```

## 🛠️ Ideas to Extend

- Add a `discount` field for sale items
- Add a `rating` field (1–5 stars)
- Split into multiple JSON files by category
- Connect to a real database (PostgreSQL, MongoDB)
- Build a full REST API with Node.js + Express

## 📄 License

MIT — free to use in personal and commercial projects.
