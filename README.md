import React from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { Phone, Clock, MapPin, ShoppingCart, MessageCircle, Star, Navigation } from "lucide-react"; import { motion } from "framer-motion";

const products = [ { name: "Tukul", price: "RM25", img: "/tools/hammer.jpg" }, { name: "Set Pemutar Skru", price: "RM45", img: "/tools/screwdriver.jpg" }, { name: "Gerudi Elektrik", price: "RM199", img: "/tools/drill.jpg" }, { name: "Paku (1kg)", price: "RM10", img: "/tools/nails.jpg" }, { name: "Sepana Paip", price: "RM35", img: "/tools/wrench.jpg" }, ];

const reviews = [ { name: "Ah Ming", comment: "Harga berpatutan, servis bagus!", rating: 5 }, { name: "Encik Zhang", comment: "Gerudi elektrik sangat berguna!", rating: 4 }, { name: "Cikgu Chen", comment: "Barang lengkap dan bos mesra.", rating: 5 }, ];

export default function HardwareStore() { return ( <div className="min-h-screen bg-gradient-to-br from-gray-100 to-gray-200 py-10 px-6"> <div className="max-w-6xl mx-auto"> {/* Header */} <motion.header className="mb-12 text-center" initial={{ opacity: 0, y: -30 }} animate={{ opacity: 1, y: 0 }} transition={{ duration: 0.6 }} > <h1 className="text-5xl font-bold mb-4 text-gray-800">Kedai Perkakasan</h1> <div className="flex flex-col items-center gap-1 text-gray-600 text-lg"> <div className="flex items-center gap-2"><MapPin size={18}/> Jalan Bidara 10, Bandar Saujana Utama, 47000 Sungai Buloh, Selangor</div> <div className="flex items-center gap-2"><Phone size={18}/> 012-6747046</div> <div className="flex items-center gap-2"><Clock size={18}/> Waktu Operasi: 8:30 pagi - 5:30 petang</div> </div> <div className="flex justify-center gap-4 mt-5"> <a 
href="https://wa.me/60126747046" 
target="_blank" 
rel="noopener noreferrer"
className="inline-flex items-center px-5 py-2 bg-green-500 hover:bg-green-600 text-white rounded-full text-lg shadow-md"
> <MessageCircle className="mr-2" size={18}/> WhatsApp Sekarang </a> <a 
href="https://maps.google.com/?q=Jalan+Bidara+10,+Bandar+Saujana+Utama" 
target="_blank" 
rel="noopener noreferrer"
className="inline-flex items-center px-5 py-2 bg-blue-500 hover:bg-blue-600 text-white rounded-full text-lg shadow-md"
> <Navigation className="mr-2" size={18}/> Arah ke Kedai </a> </div> </motion.header>

{/* Product Section */}
    <section>
      <h2 className="text-3xl font-semibold mb-6 text-gray-800">Produk Popular</h2>
      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        {products.map((product, index) => (
          <motion.div 
            key={index} 
            initial={{ opacity: 0, scale: 0.9 }} 
            animate={{ opacity: 1, scale: 1 }} 
            transition={{ delay: index * 0.1 }}
          >
            <Card className="rounded-2xl shadow-xl hover:shadow-2xl transition duration-300 overflow-hidden">
              <img src={product.img} alt={product.name} className="w-full h-48 object-cover" />
              <CardContent className="p-6">
                <h3 className="text-2xl font-bold mb-2 text-gray-700">{product.name}</h3>
                <p className="text-gray-600 mb-4">Harga: {product.price}</p>
                <Button className="w-full"><ShoppingCart className="mr-2" size={18}/> Beli Sekarang</Button>
              </CardContent>
            </Card>
          </motion.div>
        ))}
      </div>
    </section>

    {/* Review Section */}
    <section className="mt-16">
      <h2 className="text-3xl font-semibold mb-6 text-gray-800">Ulasan Pelanggan</h2>
      <div className="grid grid-cols-1 md:grid-cols-3 gap-6">
        {reviews.map((review, i) => (
          <div key={i} className="bg-white p-6 rounded-xl shadow-md">
            <div className="flex items-center mb-2">
              {[...Array(review.rating)].map((…
