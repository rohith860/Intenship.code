<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Online Shopping Website</title>
    <style>
      * {
        box-sizing: border-box;
      }
      body {
        font-family: "Poppins", sans-serif;
        margin: 0;
        background-color: #0f172a;
        color: #f1f5f9;
      }
      .navbar {
        background: #1e293b;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem 2rem;
      }
      .navbar input {
        padding: 0.5rem;
        border-radius: 8px;
        border: none;
      }
      .hero {
        text-align: center;
        padding: 2rem;
        background: #3b82f6;
        color: white;
      }
      .product-grid {
        display: flex;
        justify-content: center;
        gap: 1rem;
        flex-wrap: wrap;
        padding: 1rem;
      }
      .card {
        background: #1e293b;
        padding: 1rem;
        border-radius: 12px;
        text-align: center;
        width: 200px;
        transition: 0.3s;
      }
      .card:hover {
        transform: scale(1.05);
      }
      .buy-btn {
        background: #3b82f6;
        color: white;
        border: none;
        padding: 0.5rem 1rem;
        border-radius: 8px;
        cursor: pointer;
      }
      .category-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
        gap: 1rem;
        padding: 1rem;
      }
      .category-item {
        background: #3b82f6;
        padding: 1rem;
        border-radius: 8px;
        text-align: center;
        color: white;
        font-weight: bold;
      }
    </style>
  </head>
  <body>
    <div id="root"></div>

   <!-React + Babel Libraries-->
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
<!-React app code-->
    <script type="text/babel">
      const Navbar = () => (
        <nav className="navbar">
          <h2 className="logo">ShopEase</h2>
          <input type="text" placeholder="Search products..." />
          <button>Cart</button>
        </nav>
      );
<!- React online shopping -->
      const ProductCard = ({ name, price, image }) => (
        <div className="card">
          <img src={image} alt={name} width="120" height="120" />
          <h3>{name}</h3>
          <p>{price}</p>
          <button className="buy-btn">Add to Cart</button>
        </div>
      );
<App of shopping cart>
      const CategoryGrid = () => {
        const categories = [
          "Phones",
          "Laptops",
          "Cameras",
          "Watches",
          "Headphones",
          "Speakers",
          "Clothing",
          "Shoes",
          "Books",
          "Toys",
        ];
        return (
          <div className="category-grid">
            {categories.map((cat, i) => (
              <div key={i} className="category-item">
                {cat}
              </div>
            ))}
          </div>
        );
      };
<product of shopping >
      const App = () => {
        const products = [
          {
            id: 1,
            name: "Wireless Headphone",
            price: "$59.99",
            image: "https://via.placeholder.com/120",
          },
          {
            id: 2,
            name: "Smartwatch",
            price: "$199.99",
            image: "https://via.placeholder.com/120",
          },
          {
            id: 3,
            name: "Gaming Controller",
            price: "$49.99",
            image: "https://via.placeholder.com/120",
          },
          {
            id: 4,
            name: "Smart Speaker",
            price: "$79.99",
       image:
"https://via.placeholder.com/120",
},
];

        return (
          <div>
            <Navbar />
            <header className="hero">
              <h1>Explore the Latest Trends</h1>
              <p>Find your favorite gadgets and accessories</p>
            </header>

            <section>
              <h2 style={{ textAlign: "center" }}>Popular Products</h2>
              <div className="product-grid">
                {products.map((p) => (
                  <ProductCard key={p.id} {...p} />
                ))}
              </div>
            </section>

            <section>
              <h2 style={{ textAlign: "center" }}>Shop by Category</h2>
              <CategoryGrid />
            </section>
          </div>
        );
      };

      const root = ReactDOM.createRoot(document.getElementById("root"));
      root.render(<App />);
    </script>
  </body>
</html>
