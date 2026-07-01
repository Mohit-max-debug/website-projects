# website-projects
fronted part of website 



import { BrowserRouter, Routes, Route } from "react-router-dom";
import Navbar from "./components/Navbar";
import Home from "./pages/Home";
import Products from "./pages/Products";
import About from "./pages/About";

function App() {
  return (
    <BrowserRouter>
      <Navbar />

      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/products" element={<Products />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}

export default App;



//////////////////////////////////////////////
components/Navbar.jsx
import { Link } from "react-router-dom";

function Navbar() {
  return (
    <nav
      style={{
        display: "flex",
        justifyContent: "space-between",
        padding: "15px 40px",
        background: "#222",
        color: "white",
      }}
    >
      <h2>My Store</h2>

      <div style={{ display: "flex", gap: "20px" }}>
        <Link to="/" style={{ color: "white" }}>
          Home
        </Link>

        <Link to="/products" style={{ color: "white" }}>
          Products
        </Link>

        <Link to="/about" style={{ color: "white" }}>
          About
        </Link>
      </div>
    </nav>
  );
}

export default Navbar; 
////////////////////////////////////////////////////////////////////
components/ProductCard.jsx
function ProductCard({ title, price }) {
  return (
    <div
      style={{
        border: "1px solid gray",
        padding: "20px",
        width: "220px",
        borderRadius: "8px",
      }}
    >
      <h3>{title}</h3>

      <p>Price: ₹{price}</p>

      <button>Add to Cart</button>
    </div>
  );
}

export default ProductCard;


//////////////////////////////////////////////////////////////////////////
pages/Home.jsx
function Home() {
  return (
    <div style={{ padding: "40px" }}>
      <h1>Welcome to My Store</h1>

      <p>Buy amazing products at affordable prices.</p>
    </div>
  );
}

export default Home;

/////////////////////////////////////////////////////////////////////////////
import ProductCard from "../components/ProductCard";

function Products() {
  const products = [
    { id: 1, title: "Laptop", price: 55000 },
    { id: 2, title: "Phone", price: 25000 },
    { id: 3, title: "Headphones", price: 3000 },
    { id: 4, title: "Smart Watch", price: 5000 },
  ];

  return (
    <div style={{ padding: "40px" }}>
      <h1>Products</h1>

      <div
        style={{
          display: "flex",
          gap: "20px",
          flexWrap: "wrap",
          marginTop: "20px",
        }}
      >
        {products.map((item) => (
          <ProductCard
            key={item.id}
            title={item.title}
            price={item.price}
          />
        ))}
      </div>
    </div>
  );
}

export default Products;



///////////////////////////////////////////////////////////////////////////
pages/About.jsx
function About() {
  return (
    <div style={{ padding: "40px" }}>
      <h1>About Us</h1>

      <p>This is a simple React Product Catalog website.</p>
    </div>
  );
}

export default About;



//////////////////////////////////////////////////////////////////////////////
Create the project
npm create vite@latest product-catalog -- --template react
cd product-catalog

npm install

npm install react-router-dom
npm install -D tailwindcss @tailwindcss/vite

npm run dev
