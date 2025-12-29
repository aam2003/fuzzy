# fuzzy
my first repository on github
Hello world
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";
import { ShoppingCart, Star } from "lucide-react";

export default function OnlineStore() {
  const products = [
    { name: "Smart Watch", price: "$49", rating: 4.5 },
    { name: "Wireless Headphones", price: "$79", rating: 4.7 },
    { name: "Running Shoes", price: "$59", rating: 4.3 },
    { name: "Backpack", price: "$39", rating: 4.4 },
    { name: "Mobile Phone", price: "$299", rating: 4.6 },
    { name: "Laptop", price: "$699", rating: 4.8 },
  ];

  return (
    <div className="min-h-screen bg-gray-50 text-gray-800">
      {/* Header */}
      <header className="bg-blue-600 text-white py-4 px-6 flex justify-between items-center">
        <h1 className="text-2xl font-bold">ShopEasy</h1>
        <Button className="bg-white text-blue-600 rounded-2xl flex gap-2">
          <ShoppingCart /> Cart
        </Button>
      </header>

      {/* Hero */}
      <section className="bg-gradient-to-r from-blue-500 to-indigo-600 text-white py-20 text-center px-6">
        <motion.div
          initial={{ opacity: 0, y: 30 }}
          animate={{ opacity: 1, y: 0 }}
          transition={{ duration: 0.6 }}
        >
          <h2 className="text-4xl md:text-5xl font-bold mb-4">Buy Anything Online</h2>
          <p className="text-lg mb-6">Best prices • Fast delivery • Secure payment</p>
          <Button className="bg-white text-blue-600 rounded-2xl px-6 py-3">
            Start Shopping
          </Button>
        </motion.div>
      </section>

      {/* Products */}
      <section className="py-16 px-6 max-w-7xl mx-auto">
        <h2 className="text-3xl font-semibold text-center mb-12">Featured Products</h2>
        <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
          {products.map((product) => (
            <motion.div key={product.name} whileHover={{ scale: 1.05 }}>
              <Card className="rounded-2xl shadow-md">
                <CardContent className="p-6">
                  <div className="h-40 bg-gray-200 rounded-xl mb-4"></div>
                  <h3 className="text-xl font-medium">{product.name}</h3>
                  <p className="text-blue-600 font-semibold mt-2">{product.price}</p>
                  <div className="flex items-center gap-1 text-yellow-500 mt-2">
                    <Star size={16} /> {product.rating}
                  </div>
                  <Button className="w-full mt-4 rounded-xl">Add to Cart</Button>
                </CardContent>
              </Card>
            </motion.div>
          ))}
        </div>
      </section>

      {/* Footer */}
      <footer className="bg-gray-900 text-gray-300 py-6 text-center">
        <p>© 2025 ShopEasy. All rights reserved.</p>
      </footer>
    </div>
  );
}
