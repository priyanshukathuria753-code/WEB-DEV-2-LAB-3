
Node.js + Express + MongoDB (Mongoose) + dotenv

## Setup
1. Install MongoDB and make sure it is running (or use a MongoDB Atlas URL).
2. `npm install`
3. Check `.env` (PORT and MONGO_URI)
4. (Optional) `npm run seed` to add 12 sample products
5. `npm start`  -> http://localhost:5000

## API Endpoints
| Method | URL | What it does |
|--------|-----|--------------|
| POST   | /api/products | Create product |
| GET    | /api/products | List products (filter, sort, paginate) |
| GET    | /api/products/:id | Get one product |
| PUT    | /api/products/:id | Update product details |
| PATCH  | /api/products/:id/stock | Restock / sale (`{"change": 10}` or `{"change": -3}`) |
| DELETE | /api/products/:id | Delete product |
| GET    | /api/products/low-stock | Products with quantity <= reorderLevel |
| GET    | /api/products/summary | Category-wise summary (aggregation) |

## Query examples
- `/api/products?category=Electronics`
- `/api/products?minPrice=500&maxPrice=5000`
- `/api/products?search=pen`
- `/api/products?sort=-price` (high to low) or `sort=price`
- `/api/products?page=2&limit=5`

## Sample POST body
```json
{ "name": "Gel Pen Pack of 15", "sku": "STNY-PN-713", "category": "Stationery",
  "price": 120, "quantity": 40, "reorderLevel": 20, "supplier": "Cello Pens" }
```

<img width="1433" height="957" alt="Screenshot 2026-11-18 120857" src="https://github.com/user-attachments/assets/d896bab8-1e56-4013-b129-42e1a6ebf413" />
<img width="1442" height="958" alt="Screenshot 2026-11-18 121743" src="https://github.com/user-attachments/assets/f71f6fdb-6dca-487b-be80-f39d11784dd7" />

<img width="1445" height="962" alt="Screenshot 2026-11-18 122957" src="https://github.com/user-attachments/assets/16e66a69-78c3-4aec-beee-351c4e149165" />

<img width="1422" height="941" alt="Screenshot 2026-11-18 122123" src="https://github.com/user-attachments/assets/15d2e32c-23e7-4c95-9c1a-1bbd3b325b1d" />
<img width="1448" height="922" alt="Screenshot 2026-11-18 122148" src="https://github.com/user-attachments/assets/9d91926f-13e0-45ad-92d9-666a2931f14f" />
<img width="1407" height="953" alt="Screenshot 2026-11-18 122220" src="https://github.com/user-attachments/assets/7decd620-9e3a-43dc-9d37-261e2d5e28a0" />
<img width="1447" height="990" alt="Screenshot 2026-11-18 122244" src="https://github.com/user-attachments/assets/dd35097a-2a64-4627-824e-99b21a77145c" />


