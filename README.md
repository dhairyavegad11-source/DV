<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LUMIÈRE & CO. — Modern Apparel, Accessories & Fragrances</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Plus Jakarta Sans', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#fdf8f6',
                            100: '#f2e8e5',
                            600: '#9b4d31',
                            700: '#7d3d25',
                            900: '#4a2315',
                        }
                    }
                }
            }
        }
    </script>
    <style>
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f1f1;
        }
        ::-webkit-scrollbar-thumb {
            background: #d1d5db;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #9ca3af;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-in {
            animation: fadeIn 0.3s ease-out forwards;
        }
    </style>
</head>
<body class="bg-gray-50 text-gray-900 font-sans antialiased min-h-screen flex flex-col justify-between">

    <header class="sticky top-0 z-40 bg-white/95 backdrop-blur-md border-b border-gray-100 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-20">
                <!-- Brand Logo -->
                <div class="flex items-center space-x-3 cursor-pointer" onclick="resetStore()">
                    <div class="w-10 h-10 rounded-xl bg-gray-900 text-white flex items-center justify-center font-bold text-xl tracking-wider">L</div>
                    <div>
                        <span class="text-xl font-extrabold tracking-widest text-gray-900">LUMIÈRE</span>
                        <span class="block text-[10px] tracking-widest text-gray-500 uppercase font-semibold">Clothing • Accessories • Perfume</span>
                    </div>
                </div>

                <!-- Desktop Nav Links -->
                <nav class="hidden md:flex items-center space-x-8 text-sm font-medium text-gray-600">
                    <button onclick="filterCategory('All')" class="hover:text-gray-900 transition-colors py-2 border-b-2 border-transparent hover:border-gray-900">All Products</button>
                    <button onclick="filterCategory('Clothing')" class="hover:text-gray-900 transition-colors py-2 border-b-2 border-transparent hover:border-gray-900">Clothing</button>
                    <button onclick="filterCategory('Accessories')" class="hover:text-gray-900 transition-colors py-2 border-b-2 border-transparent hover:border-gray-900">Accessories</button>
                    <button onclick="filterCategory('Perfumes')" class="hover:text-gray-900 transition-colors py-2 border-b-2 border-transparent hover:border-gray-900">Perfumes</button>
                </nav>

                <!-- Search & Actions -->
                <div class="flex items-center space-x-4">
                    <div class="relative hidden sm:block w-48 lg:w-64">
                        <span class="absolute inset-y-0 left-0 flex items-center pl-3 pointer-events-none text-gray-400">
                            <i class="fa-solid fa-search text-xs"></i>
                        </span>
                        <input type="text" id="searchInput" oninput="handleSearch()" placeholder="Search items..." class="w-full pl-9 pr-4 py-2 bg-gray-100 border-none rounded-full text-sm focus:outline-none focus:ring-2 focus:ring-gray-900 transition-all">
                    </div>

                    <!-- Cart Trigger Button -->
                    <button onclick="toggleCartDrawer(true)" class="relative p-2.5 bg-gray-100 hover:bg-gray-200 text-gray-800 rounded-full transition-all flex items-center justify-center">
                        <i class="fa-solid fa-bag-shopping text-base"></i>
                        <span id="cartBadge" class="absolute -top-1 -right-1 bg-gray-900 text-white text-[10px] font-bold w-5 h-5 rounded-full flex items-center justify-center shadow-md">0</span>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <main class="flex-grow">
        <!-- Hero Banner -->
        <section class="relative bg-gray-900 text-white overflow-hidden py-16 lg:py-24">
            <div class="absolute inset-0 opacity-45 mix-blend-overlay">
                <img src="https://images.unsplash.com/photo-1441986300917-64674bd600d8?auto=format&fit=crop&q=80&w=1600" alt="Hero background" class="w-full h-full object-cover">
            </div>
            <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center sm:text-left flex flex-col sm:flex-row items-center justify-between">
                <div class="max-w-xl">
                    <span class="inline-block py-1 px-3 rounded-full bg-white/10 text-white text-xs font-semibold tracking-widest uppercase mb-4 backdrop-blur-md">New Autumn/Winter Collection</span>
                    <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold tracking-tight mb-6 leading-tight">Elevate Your Everyday Style.</h1>
                    <p class="text-gray-300 text-base sm:text-lg mb-8">Discover our curated selection of premium apparel, handcrafted leather accessories, and signature luxury fragrances.</p>
                    <div class="flex flex-wrap gap-4 justify-center sm:justify-start">
                        <a href="#shopSection" class="px-8 py-3.5 bg-white text-gray-900 font-semibold rounded-full shadow-lg hover:bg-gray-100 transition-all transform hover:-translate-y-0.5">Explore Collection</a>
                        <button onclick="filterCategory('Perfumes')" class="px-8 py-3.5 bg-transparent border-2 border-white text-white font-semibold rounded-full hover:bg-white/10 transition-all">Shop Perfumes</button>
                    </div>
                </div>
                <div class="mt-10 sm:mt-0 grid grid-cols-2 gap-4 max-w-xs">
                    <div class="bg-white/10 backdrop-blur-md p-4 rounded-2xl border border-white/10 text-center">
                        <span class="block text-2xl font-bold">100%</span>
                        <span class="text-xs text-gray-300">Authentic Materials</span>
                    </div>
                    <div class="bg-white/10 backdrop-blur-md p-4 rounded-2xl border border-white/10 text-center">
                        <span class="block text-2xl font-bold">Fast</span>
                        <span class="text-xs text-gray-300">Express Delivery</span>
                    </div>
                </div>
            </div>
        </section>

        <section id="shopSection" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
            <div class="flex flex-col md:flex-row md:items-end justify-between mb-10 pb-6 border-b border-gray-200">
                <div>
                    <h2 class="text-3xl font-bold text-gray-900 tracking-tight" id="sectionTitle">All Products</h2>
                    <p class="text-sm text-gray-500 mt-1">Browse our latest arrivals hand-picked for style and quality.</p>
                </div>
                <!-- Category Pills & Sort -->
                <div class="mt-6 md:mt-0 flex flex-wrap items-center gap-3">
                    <div class="flex bg-gray-200/80 p-1 rounded-xl text-sm font-medium">
                        <button onclick="filterCategory('All')" id="btn-All" class="cat-btn px-4 py-2 rounded-lg bg-white text-gray-900 shadow-sm transition-all">All</button>
                        <button onclick="filterCategory('Clothing')" id="btn-Clothing" class="cat-btn px-4 py-2 rounded-lg text-gray-600 hover:text-gray-900 transition-all">Clothing</button>
                        <button onclick="filterCategory('Accessories')" id="btn-Accessories" class="cat-btn px-4 py-2 rounded-lg text-gray-600 hover:text-gray-900 transition-all">Accessories</button>
                        <button onclick="filterCategory('Perfumes')" id="btn-Perfumes" class="cat-btn px-4 py-2 rounded-lg text-gray-600 hover:text-gray-900 transition-all">Perfumes</button>
                    </div>
                    <select id="sortBy" onchange="sortProducts()" class="bg-gray-100 border border-gray-200 text-gray-700 text-sm rounded-xl px-4 py-2.5 focus:outline-none focus:ring-2 focus:ring-gray-900">
                        <option value="featured">Sort by: Featured</option>
                        <option value="low-high">Price: Low to High</option>
                        <option value="high-low">Price: High to Low</option>
                        <option value="rating">Highest Rated</option>
                    </select>
                </div>
            </div>

            <!-- Product Grid -->
            <div id="productGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- Dynamically populated via JavaScript -->
            </div>

            <!-- Empty State -->
            <div id="emptyState" class="hidden text-center py-24">
                <div class="w-16 h-16 bg-gray-100 text-gray-400 rounded-full flex items-center justify-center mx-auto mb-4 text-2xl">
                    <i class="fa-solid fa-box-open"></i>
                </div>
                <h3 class="text-lg font-bold text-gray-800">No products found</h3>
                <p class="text-sm text-gray-500 mt-1">Try adjusting your search or category filter.</p>
                <button onclick="resetStore()" class="mt-4 px-6 py-2.5 bg-gray-900 text-white rounded-full text-sm font-medium hover:bg-gray-800 transition-all">Reset Filters</button>
            </div>
        </section>
    </main>

    <div id="productModal" class="fixed inset-0 z-50 hidden bg-black/60 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-4xl w-full overflow-hidden shadow-2xl relative animate-fade-in flex flex-col md:flex-row">
            <button onclick="closeProductModal()" class="absolute top-4 right-4 z-10 w-10 h-10 bg-white/80 hover:bg-white text-gray-800 rounded-full flex items-center justify-center shadow-md transition-all">
                <i class="fa-solid fa-xmark text-lg"></i>
            </button>
            <div class="md:w-1/2 bg-gray-100 relative h-72 md:h-auto">
                <img id="modalImg" src="" alt="Product" class="w-full h-full object-cover">
            </div>
            <div class="md:w-1/2 p-8 flex flex-col justify-between">
                <div>
                    <span id="modalCategory" class="text-xs font-bold tracking-widest text-gray-400 uppercase"></span>
                    <h3 id="modalTitle" class="text-2xl font-extrabold text-gray-900 mt-1 mb-2"></h3>
                    <div class="flex items-center space-x-2 mb-4">
                        <div class="flex text-amber-400 text-sm" id="modalStars"></div>
                        <span id="modalRating" class="text-xs text-gray-500 font-medium"></span>
                    </div>
                    <div class="text-3xl font-extrabold text-gray-900 mb-6" id="modalPrice"></div>
                    <p id="modalDesc" class="text-gray-600 text-sm leading-relaxed mb-6"></p>
                    
                    <!-- Options (Size/Variants if available) -->
                    <div id="modalVariantContainer" class="mb-6">
                        <label class="block text-xs font-bold text-gray-700 uppercase mb-2">Select Size / Variant</label>
                        <div class="flex gap-2" id="modalVariantOptions">
                            <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900 focus:border-gray-900 focus:ring-2 focus:ring-gray-900">S</button>
                            <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900 focus:border-gray-900 focus:ring-2 focus:ring-gray-900">M</button>
                            <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900 focus:border-gray-900 focus:ring-2 focus:ring-gray-900">L</button>
                            <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900 focus:border-gray-900 focus:ring-2 focus:ring-gray-900">XL</button>
                        </div>
                    </div>
                </div>

                <div class="flex items-center space-x-4 pt-6 border-t border-gray-100">
                    <div class="flex items-center border border-gray-300 rounded-xl">
                        <button onclick="adjustModalQty(-1)" class="px-4 py-3 text-gray-600 hover:text-gray-900 font-bold">-</button>
                        <span id="modalQty" class="px-4 py-3 font-semibold text-gray-900">1</span>
                        <button onclick="adjustModalQty(1)" class="px-4 py-3 text-gray-600 hover:text-gray-900 font-bold">+</button>
                    </div>
                    <button id="modalAddToCartBtn" class="flex-grow py-3.5 bg-gray-900 hover:bg-gray-800 text-white font-semibold rounded-xl shadow-lg transition-all flex items-center justify-center space-x-2">
                        <i class="fa-solid fa-bag-shopping"></i>
                        <span>Add to Cart</span>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <div id="cartDrawer" class="fixed inset-0 z-50 hidden">
        <div class="absolute inset-0 bg-black/50 backdrop-blur-sm transition-opacity" onclick="toggleCartDrawer(false)"></div>
        <div class="absolute inset-y-0 right-0 max-w-md w-full bg-white shadow-2xl flex flex-col transform transition-transform duration-300">
            <!-- Cart Header -->
            <div class="p-6 border-b border-gray-100 flex items-center justify-between">
                <div class="flex items-center space-x-2">
                    <i class="fa-solid fa-bag-shopping text-gray-900 text-lg"></i>
                    <h3 class="font-bold text-lg text-gray-900">Your Shopping Cart</h3>
                    <span id="cartCountBadge" class="ml-2 bg-gray-100 text-gray-800 text-xs px-2.5 py-0.5 rounded-full font-semibold">0 items</span>
                </div>
                <button onclick="toggleCartDrawer(false)" class="p-2 text-gray-400 hover:text-gray-600 rounded-full transition-all">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>

            <!-- Cart Items List -->
            <div id="cartItemsList" class="flex-grow overflow-y-auto p-6 space-y-4 divide-y divide-gray-100">
                <!-- Dynamically populated -->
            </div>

            <!-- Empty Cart Message -->
            <div id="emptyCart" class="hidden flex-grow flex flex-col items-center justify-center p-6 text-center">
                <div class="w-16 h-16 bg-gray-100 text-gray-400 rounded-full flex items-center justify-center mb-4 text-2xl">
                    <i class="fa-solid fa-bag-shopping"></i>
                </div>
                <h4 class="font-bold text-gray-800 text-lg">Your cart is empty</h4>
                <p class="text-sm text-gray-500 mt-1 mb-6">Discover our collections and add your favorite items.</p>
                <button onclick="toggleCartDrawer(false)" class="px-6 py-3 bg-gray-900 text-white text-sm font-semibold rounded-xl hover:bg-gray-800 transition-all">Start Shopping</button>
            </div>

            <!-- Cart Footer & Subtotal -->
            <div id="cartFooter" class="p-6 border-t border-gray-100 bg-gray-50/50">
                <div class="space-y-2 mb-6">
                    <div class="flex justify-between text-sm text-gray-600">
                        <span>Subtotal</span>
                        <span id="cartSubtotal" class="font-semibold text-gray-900">₹0.00</span>
                    </div>
                    <div class="flex justify-between text-sm text-gray-600">
                        <span>Estimated Shipping</span>
                        <span class="font-semibold text-green-600">Free</span>
                    </div>
                    <div class="flex justify-between text-base font-bold text-gray-900 pt-2 border-t border-gray-200">
                        <span>Total</span>
                        <span id="cartTotal">₹0.00</span>
                    </div>
                </div>
                <button onclick="openCheckout()" class="w-full py-4 bg-gray-900 hover:bg-gray-800 text-white font-bold rounded-2xl shadow-lg transition-all flex items-center justify-center space-x-2">
                    <span>Proceed to Checkout</span>
                    <i class="fa-solid fa-arrow-right text-sm"></i>
                </button>
            </div>
        </div>
    </div>

    <div id="checkoutModal" class="fixed inset-0 z-50 hidden bg-black/60 backdrop-blur-sm flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-white rounded-3xl max-w-2xl w-full overflow-hidden shadow-2xl relative animate-fade-in my-8">
            <!-- Header -->
            <div class="p-6 border-b border-gray-100 flex items-center justify-between bg-gray-50">
                <div>
                    <h3 class="text-xl font-extrabold text-gray-900">Secure Checkout</h3>
                    <p class="text-xs text-gray-500 mt-0.5">Please provide your delivery and payment details.</p>
                </div>
                <button onclick="closeCheckout()" class="p-2 text-gray-400 hover:text-gray-600 rounded-full transition-all">
                    <i class="fa-solid fa-xmark text-lg"></i>
                </button>
            </div>

            <!-- Checkout Form -->
            <form id="checkoutForm" onsubmit="handleCheckoutSubmit(event)" class="p-6 space-y-6">
                <!-- Customer Details -->
                <div>
                    <h4 class="text-sm font-bold text-gray-900 uppercase tracking-wider mb-4">1. Customer Information</h4>
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <div>
                            <label class="block text-xs font-semibold text-gray-700 mb-1">Full Name</label>
                            <input type="text" id="custName" required placeholder="John Doe" class="w-full px-4 py-2.5 bg-gray-50 border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900">
                        </div>
                        <div>
                            <label class="block text-xs font-semibold text-gray-700 mb-1">Email Address</label>
                            <input type="email" id="custEmail" required placeholder="john@example.com" class="w-full px-4 py-2.5 bg-gray-50 border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900">
                        </div>
                        <div class="sm:col-span-2">
                            <label class="block text-xs font-semibold text-gray-700 mb-1">Phone Number</label>
                            <input type="tel" id="custPhone" required placeholder="+91 98765 43210" class="w-full px-4 py-2.5 bg-gray-50 border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900">
                        </div>
                        <div class="sm:col-span-2">
                            <label class="block text-xs font-semibold text-gray-700 mb-1">Delivery Address</label>
                            <textarea id="custAddress" required rows="2" placeholder="Street address, apartment, city, state, pincode" class="w-full px-4 py-2.5 bg-gray-50 border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900"></textarea>
                        </div>
                    </div>
                </div>

                <!-- Payment Options -->
                <div>
                    <h4 class="text-sm font-bold text-gray-900 uppercase tracking-wider mb-4">2. Payment Method</h4>
                    <div class="grid grid-cols-1 sm:grid-cols-3 gap-3">
                        <label class="border border-gray-200 rounded-2xl p-4 flex flex-col items-center justify-center cursor-pointer hover:border-gray-900 transition-all has-[:checked]:border-gray-900 has-[:checked]:bg-gray-50">
                            <input type="radio" name="paymentMethod" value="UPI" checked onclick="togglePaymentFields('UPI')" class="mb-2 accent-gray-900">
                            <i class="fa-solid fa-mobile-screen text-xl mb-1 text-gray-800"></i>
                            <span class="text-xs font-bold text-gray-800">UPI / QR</span>
                        </label>
                        <label class="border border-gray-200 rounded-2xl p-4 flex flex-col items-center justify-center cursor-pointer hover:border-gray-900 transition-all has-[:checked]:border-gray-900 has-[:checked]:bg-gray-50">
                            <input type="radio" name="paymentMethod" value="Card" onclick="togglePaymentFields('Card')" class="mb-2 accent-gray-900">
                            <i class="fa-solid fa-credit-card text-xl mb-1 text-gray-800"></i>
                            <span class="text-xs font-bold text-gray-800">Credit / Debit Card</span>
                        </label>
                        <label class="border border-gray-200 rounded-2xl p-4 flex flex-col items-center justify-center cursor-pointer hover:border-gray-900 transition-all has-[:checked]:border-gray-900 has-[:checked]:bg-gray-50">
                            <input type="radio" name="paymentMethod" value="COD" onclick="togglePaymentFields('COD')" class="mb-2 accent-gray-900">
                            <i class="fa-solid fa-money-bill-wave text-xl mb-1 text-gray-800"></i>
                            <span class="text-xs font-bold text-gray-800">Cash on Delivery</span>
                        </label>
                    </div>

                    <!-- Payment Sub-fields -->
                    <div id="upiFields" class="mt-4 p-4 bg-gray-50 rounded-2xl border border-gray-200">
                        <label class="block text-xs font-semibold text-gray-700 mb-1">UPI ID / VPA</label>
                        <input type="text" placeholder="username@oksbi / username@ybl" class="w-full px-4 py-2 bg-white border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900">
                    </div>

                    <div id="cardFields" class="mt-4 p-4 bg-gray-50 rounded-2xl border border-gray-200 hidden space-y-3">
                        <div>
                            <label class="block text-xs font-semibold text-gray-700 mb-1">Card Number</label>
                            <input type="text" placeholder="4532 •••• •••• 8901" class="w-full px-4 py-2 bg-white border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900">
                        </div>
                        <div class="grid grid-cols-2 gap-3">
                            <div>
                                <label class="block text-xs font-semibold text-gray-700 mb-1">Expiry Date</label>
                                <input type="text" placeholder="MM/YY" class="w-full px-4 py-2 bg-white border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900">
                            </div>
                            <div>
                                <label class="block text-xs font-semibold text-gray-700 mb-1">CVV</label>
                                <input type="password" placeholder="123" maxlength="4" class="w-full px-4 py-2 bg-white border border-gray-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-gray-900">
                            </div>
                        </div>
                    </div>

                    <div id="codFields" class="mt-4 p-4 bg-gray-50 rounded-2xl border border-gray-200 hidden text-xs text-gray-600">
                        <i class="fa-solid fa-circle-info mr-1 text-gray-800"></i> Please keep exact change ready at the time of delivery. Additional verification may be required.
                    </div>
                </div>

                <!-- Order Summary in Checkout -->
                <div class="bg-gray-50 p-4 rounded-2xl border border-gray-200 flex items-center justify-between">
                    <div>
                        <span class="block text-xs text-gray-500 font-semibold">Total Payable Amount</span>
                        <span id="checkoutTotalAmount" class="text-xl font-extrabold text-gray-900">₹0.00</span>
                    </div>
                    <button type="submit" class="px-8 py-3.5 bg-gray-900 hover:bg-gray-800 text-white font-bold rounded-xl shadow-lg transition-all">Complete Order</button>
                </div>
            </form>
        </div>
    </div>

    <div id="confirmationModal" class="fixed inset-0 z-50 hidden bg-black/60 backdrop-blur-sm flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-lg w-full p-8 text-center shadow-2xl relative animate-fade-in">
            <div class="w-16 h-16 bg-green-100 text-green-600 rounded-full flex items-center justify-center mx-auto mb-6 text-2xl shadow-inner">
                <i class="fa-solid fa-check"></i>
            </div>
            <span class="text-xs font-bold tracking-widest text-green-600 uppercase">Order Confirmed Successfully</span>
            <h3 class="text-2xl font-extrabold text-gray-900 mt-2 mb-1">Thank you for your purchase!</h3>
            <p class="text-sm text-gray-500 mb-6">We have received your order and are getting it ready for shipment.</p>
            
            <div class="bg-gray-50 rounded-2xl p-4 text-left text-sm space-y-2 mb-6 border border-gray-100">
                <div class="flex justify-between"><span class="text-gray-500">Order ID:</span><span id="confirmOrderId" class="font-bold text-gray-900">#LUM-84920</span></div>
                <div class="flex justify-between"><span class="text-gray-500">Customer Name:</span><span id="confirmCustomerName" class="font-medium text-gray-900"></span></div>
                <div class="flex justify-between"><span class="text-gray-500">Payment Mode:</span><span id="confirmPaymentMode" class="font-medium text-gray-900"></span></div>
                <div class="flex justify-between pt-2 border-t border-gray-200 font-bold"><span class="text-gray-900">Total Paid:</span><span id="confirmTotal" class="text-gray-900"></span></div>
            </div>

            <button onclick="finishOrder()" class="w-full py-3.5 bg-gray-900 hover:bg-gray-800 text-white font-bold rounded-xl shadow-lg transition-all">Continue Shopping</button>
        </div>
    </div>

    <!-- Toast Notification -->
    <div id="toast" class="fixed bottom-6 right-6 z-50 transform translate-y-20 opacity-0 transition-all duration-300 bg-gray-900 text-white px-6 py-3 rounded-2xl shadow-xl flex items-center space-x-3 text-sm font-medium">
        <i class="fa-solid fa-circle-check text-green-400"></i>
        <span id="toastMsg">Item added to cart</span>
    </div>

    <footer class="bg-white border-t border-gray-100 mt-20 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center md:text-left flex flex-col md:flex-row items-center justify-between gap-6">
            <div>
                <span class="text-lg font-extrabold tracking-widest text-gray-900">LUMIÈRE & CO.</span>
                <p class="text-xs text-gray-500 mt-1">Crafting elegance in clothing, accessories, and signature scents.</p>
            </div>
            <div class="flex space-x-6 text-gray-400">
                <a href="#" class="hover:text-gray-900 transition-colors"><i class="fa-brands fa-instagram text-lg"></i></a>
                <a href="#" class="hover:text-gray-900 transition-colors"><i class="fa-brands fa-facebook text-lg"></i></a>
                <a href="#" class="hover:text-gray-900 transition-colors"><i class="fa-brands fa-twitter text-lg"></i></a>
                <a href="#" class="hover:text-gray-900 transition-colors"><i class="fa-brands fa-pinterest text-lg"></i></a>
            </div>
            <p class="text-xs text-gray-400">&copy; 2026 Lumière & Co. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Product Catalog Data with real high quality Unsplash photos
        const products = [
            {
                id: 1,
                name: "Oversized Heavyweight Hoodie",
                category: "Clothing",
                price: 2499,
                rating: 4.8,
                reviews: 124,
                image: "https://images.unsplash.com/photo-1556905055-8f358a7a47b2?auto=format&fit=crop&q=80&w=800",
                description: "Crafted from 100% organic French Terry cotton for supreme comfort and relaxed drop-shoulder styling.",
                featured: true
            },
            {
                id: 2,
                name: "Tailored Wool Blend Overcoat",
                category: "Clothing",
                price: 6999,
                rating: 4.9,
                reviews: 89,
                image: "https://images.unsplash.com/photo-1539571696357-5a69c17a67c6?auto=format&fit=crop&q=80&w=800",
                description: "An impeccably tailored overcoat featuring premium wool blend fabric, structured shoulders, and silk lining.",
                featured: true
            },
            {
                id: 3,
                name: "Minimalist Leather Chronograph",
                category: "Accessories",
                price: 4499,
                rating: 4.7,
                reviews: 210,
                image: "https://images.unsplash.com/photo-1523275335684-37898b6baf30?auto=format&fit=crop&q=80&w=800",
                description: "Sleek stainless steel case paired with genuine Italian calfskin leather strap and Japanese quartz movement.",
                featured: true
            },
            {
                id: 4,
                name: "Midnight Velvet Eau de Parfum",
                category: "Perfumes",
                price: 3499,
                rating: 4.9,
                reviews: 312,
                image: "https://images.unsplash.com/photo-1523293182086-7651a899d37f?auto=format&fit=crop&q=80&w=800",
                description: "A sensual blend of dark amber, smoky vanilla, and rare blooming night jasmine with 12+ hour longevity.",
                featured: true
            },
            {
                id: 5,
                name: "Ribbed Merino Wool Turtleneck",
                category: "Clothing",
                price: 2999,
                rating: 4.6,
                reviews: 74,
                image: "https://images.unsplash.com/photo-1624378439575-d8705ad7ae80?auto=format&fit=crop&q=80&w=800",
                description: "Luxuriously soft merino wool turtleneck offering exceptional warmth and sophisticated everyday layering.",
                featured: false
            },
            {
                id: 6,
                name: "Handcrafted Leather Tote Bag",
                category: "Accessories",
                price: 5499,
                rating: 4.8,
                reviews: 156,
                image: "https://images.unsplash.com/photo-1548036328-c9fa89d128fa?auto=format&fit=crop&q=80&w=800",
                description: "Spacious everyday tote crafted from full-grain pebbled leather with reinforced handles and brass hardware.",
                featured: true
            },
            {
                id: 7,
                name: "Citrus Blossom Extrait de Parfum",
                category: "Perfumes",
                price: 3899,
                rating: 4.7,
                reviews: 95,
                image: "https://images.unsplash.com/photo-1594035910387-fea47794261f?auto=format&fit=crop&q=80&w=800",
                description: "Energizing notes of Sicilian bergamot, neroli blossoms, and white cedarwood for an uplifting signature scent.",
                featured: false
            },
            {
                id: 8,
                name: "Classic Silk Satin Necktie",
                category: "Accessories",
                price: 1499,
                rating: 4.5,
                reviews: 63,
                image: "https://images.unsplash.com/photo-1617137984095-74e4e5e3613f?auto=format&fit=crop&q=80&w=800",
                description: "Woven from pure mulberry silk with a subtle luster, adding timeless elegance to formal attire.",
                featured: false
            },
            {
                id: 9,
                name: "Pleated High-Waist Trousers",
                category: "Clothing",
                price: 3299,
                rating: 4.8,
                reviews: 118,
                image: "https://images.unsplash.com/photo-1594633312681-425c7b97ccd1?auto=format&fit=crop&q=80&w=800",
                description: "Sophisticated pleated trousers with a relaxed wide-leg silhouette and structured waistband.",
                featured: false
            },
            {
                id: 10,
                name: "Oud Royale Luxury Fragrance",
                category: "Perfumes",
                price: 5299,
                rating: 5.0,
                reviews: 240,
                image: "https://images.unsplash.com/photo-1547887537-6158d64c35b3?auto=format&fit=crop&q=80&w=800",
                description: "Deep, resinous Agarwood (Oud) paired with rare saffron and roasted coffee bean undertones.",
                featured: true
            },
            {
                id: 11,
                name: "Polarized Aviator Sunglasses",
                category: "Accessories",
                price: 2799,
                rating: 4.6,
                reviews: 108,
                image: "https://images.unsplash.com/photo-1572635196237-14b3f281503f?auto=format&fit=crop&q=80&w=800",
                description: "Lightweight titanium frame with 100% UV-protected polarized lenses for distortion-free clarity.",
                featured: false
            },
            {
                id: 12,
                name: "Relaxed Linen Beach Shirt",
                category: "Clothing",
                price: 2199,
                rating: 4.7,
                reviews: 82,
                image: "https://images.unsplash.com/photo-1602810318383-e386cc2a3ccf?auto=format&fit=crop&q=80&w=800",
                description: "Breathable 100% French linen shirt designed for effortless summer styling and cool comfort.",
                featured: false
            }
        ];

        // State variables
        let cart = [];
        let currentCategory = 'All';
        let searchQuery = '';
        let currentModalProduct = null;
        let modalQty = 1;

        // Initialize App
        window.addEventListener('DOMContentLoaded', () => {
            renderProducts();
            updateCartBadge();
        });

        // Render Product Grid
        function renderProducts() {
            const grid = document.getElementById('productGrid');
            const emptyState = document.getElementById('emptyState');
            grid.innerHTML = '';

            let filtered = products.filter(p => {
                const matchesCategory = currentCategory === 'All' || p.category === currentCategory;
                const matchesSearch = p.name.toLowerCase().includes(searchQuery.toLowerCase()) || 
                                      p.description.toLowerCase().includes(searchQuery.toLowerCase());
                return matchesCategory && matchesSearch;
            });

            // Sort products
            const sortBy = document.getElementById('sortBy').value;
            if (sortBy === 'low-high') {
                filtered.sort((a, b) => a.price - b.price);
            } else if (sortBy === 'high-low') {
                filtered.sort((a, b) => b.price - a.price);
            } else if (sortBy === 'rating') {
                filtered.sort((a, b) => b.rating - a.rating);
            }

            if (filtered.length === 0) {
                emptyState.classList.remove('hidden');
                return;
            } else {
                emptyState.classList.add('hidden');
            }

            filtered.forEach(p => {
                const card = document.createElement('div');
                card.className = 'group bg-white rounded-3xl border border-gray-100 shadow-sm hover:shadow-xl transition-all duration-300 overflow-hidden flex flex-col justify-between';
                card.innerHTML = `
                    <div class="relative bg-gray-100 aspect-square overflow-hidden cursor-pointer" onclick="openProductModal(${p.id})">
                        <img src="${p.image}" alt="${p.name}" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                        <span class="absolute top-3 left-3 bg-white/90 backdrop-blur-md text-gray-900 text-[10px] font-bold tracking-widest uppercase px-3 py-1 rounded-full shadow-sm">${p.category}</span>
                    </div>
                    <div class="p-5 flex flex-col flex-grow justify-between">
                        <div>
                            <div class="flex items-center justify-between mb-1">
                                <div class="flex text-amber-400 text-xs">
                                    ${getStarRatingHTML(p.rating)}
                                </div>
                                <span class="text-xs text-gray-400 font-medium">(${p.reviews})</span>
                            </div>
                            <h3 onclick="openProductModal(${p.id})" class="font-bold text-gray-900 text-base mb-1 cursor-pointer hover:text-gray-600 transition-colors line-clamp-1">${p.name}</h3>
                            <p class="text-xs text-gray-500 line-clamp-2 mb-4">${p.description}</p>
                        </div>
                        <div class="flex items-center justify-between pt-4 border-t border-gray-100">
                            <span class="text-lg font-extrabold text-gray-900">₹${p.price.toLocaleString('en-IN')}</span>
                            <button onclick="addToCart(${p.id}, 1)" class="p-3 bg-gray-900 hover:bg-gray-800 text-white rounded-2xl shadow-md transition-all flex items-center justify-center">
                                <i class="fa-solid fa-bag-shopping text-sm"></i>
                            </button>
                        </div>
                    </div>
                `;
                grid.appendChild(card);
            });
        }

        function getStarRatingHTML(rating) {
            let html = '';
            for (let i = 1; i <= 5; i++) {
                if (i <= Math.floor(rating)) {
                    html += '<i class="fa-solid fa-star"></i>';
                } else if (i - rating < 1) {
                    html += '<i class="fa-solid fa-star-half-stroke"></i>';
                } else {
                    html += '<i class="fa-regular fa-star text-gray-300"></i>';
                }
            }
            return html;
        }

        // Category Filtering
        function filterCategory(category) {
            currentCategory = category;
            document.getElementById('sectionTitle').innerText = category === 'All' ? 'All Products' : category;
            
            // Update active pill styling
            document.querySelectorAll('.cat-btn').forEach(btn => {
                btn.classList.remove('bg-white', 'text-gray-900', 'shadow-sm');
                btn.classList.add('text-gray-600');
            });
            const activeBtn = document.getElementById(`btn-${category}`);
            if (activeBtn) {
                activeBtn.classList.add('bg-white', 'text-gray-900', 'shadow-sm');
                activeBtn.classList.remove('text-gray-600');
            }
            renderProducts();
        }

        function handleSearch() {
            searchQuery = document.getElementById('searchInput').value;
            renderProducts();
        }

        function sortProducts() {
            renderProducts();
        }

        function resetStore() {
            currentCategory = 'All';
            searchQuery = '';
            document.getElementById('searchInput').value = '';
            document.getElementById('sortBy').value = 'featured';
            filterCategory('All');
        }

        // Product Modal Details
        function openProductModal(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            currentModalProduct = product;
            modalQty = 1;

            document.getElementById('modalImg').src = product.image;
            document.getElementById('modalCategory').innerText = product.category;
            document.getElementById('modalTitle').innerText = product.name;
            document.getElementById('modalStars').innerHTML = getStarRatingHTML(product.rating);
            document.getElementById('modalRating').innerText = `${product.rating} (${product.reviews} reviews)`;
            document.getElementById('modalPrice').innerText = `₹${product.price.toLocaleString('en-IN')}`;
            document.getElementById('modalDesc').innerText = product.description;
            document.getElementById('modalQty').innerText = modalQty;

            const variantContainer = document.getElementById('modalVariantContainer');
            if (product.category === 'Perfumes') {
                variantContainer.style.display = 'block';
                document.getElementById('modalVariantOptions').innerHTML = `
                    <button class="px-4 py-2 border-2 border-gray-900 rounded-xl text-sm font-bold bg-gray-50">50 ml</button>
                    <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900">100 ml</button>
                `;
            } else if (product.category === 'Clothing') {
                variantContainer.style.display = 'block';
                document.getElementById('modalVariantOptions').innerHTML = `
                    <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900">S</button>
                    <button class="px-4 py-2 border-2 border-gray-900 rounded-xl text-sm font-bold bg-gray-50">M</button>
                    <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900">L</button>
                    <button class="px-4 py-2 border border-gray-300 rounded-xl text-sm font-medium hover:border-gray-900">XL</button>
                `;
            } else {
                variantContainer.style.display = 'none';
            }

            document.getElementById('modalAddToCartBtn').onclick = () => {
                addToCart(product.id, modalQty);
                closeProductModal();
            };

            document.getElementById('productModal').classList.remove('hidden');
        }

        function closeProductModal() {
            document.getElementById('productModal').classList.add('hidden');
        }

        function adjustModalQty(amount) {
            modalQty = Math.max(1, modalQty + amount);
            document.getElementById('modalQty').innerText = modalQty;
        }

        // Cart Management
        function addToCart(productId, quantity = 1) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const existingItem = cart.find(item => item.id === productId);
            if (existingItem) {
                existingItem.quantity += quantity;
            } else {
                cart.push({ ...product, quantity });
            }

            updateCartBadge();
            renderCartItems();
            showToast(`Added ${quantity}x ${product.name} to cart`);
        }

        function updateCartQuantity(productId, change) {
            const item = cart.find(i => i.id === productId);
            if (!item) return;

            item.quantity += change;
            if (item.quantity <= 0) {
                removeFromCart(productId);
            } else {
                updateCartBadge();
                renderCartItems();
            }
        }

        function removeFromCart(productId) {
            cart = cart.filter(i => i.id !== productId);
            updateCartBadge();
            renderCartItems();
            showToast('Item removed from cart');
        }

        function updateCartBadge() {
            const totalCount = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById('cartBadge').innerText = totalCount;
            document.getElementById('cartCountBadge').innerText = `${totalCount} items`;
        }

        function renderCartItems() {
            const list = document.getElementById('cartItemsList');
            const emptyCart = document.getElementById('emptyCart');
            const cartFooter = document.getElementById('cartFooter');
            list.innerHTML = '';

            if (cart.length === 0) {
                emptyCart.classList.remove('hidden');
                cartFooter.classList.add('hidden');
                return;
            } else {
                emptyCart.classList.add('hidden');
                cartFooter.classList.remove('hidden');
            }

            let subtotal = 0;

            cart.forEach(item => {
                subtotal += item.price * item.quantity;
                const div = document.createElement('div');
                div.className = 'flex items-center space-x-4 pt-4 first:pt-0';
                div.innerHTML = `
                    <img src="${item.image}" alt="${item.name}" class="w-20 h-20 object-cover rounded-2xl bg-gray-100">
                    <div class="flex-grow">
                        <h4 class="font-bold text-gray-900 text-sm line-clamp-1">${item.name}</h4>
                        <span class="text-xs text-gray-500 block mb-2">₹${item.price.toLocaleString('en-IN')}</span>
                        <div class="flex items-center justify-between">
                            <div class="flex items-center border border-gray-200 rounded-xl">
                                <button onclick="updateCartQuantity(${item.id}, -1)" class="px-2.5 py-1 text-gray-600 hover:text-gray-900 font-bold text-xs">-</button>
                                <span class="px-3 py-1 font-semibold text-xs text-gray-900">${item.quantity}</span>
                                <button onclick="updateCartQuantity(${item.id}, 1)" class="px-2.5 py-1 text-gray-600 hover:text-gray-900 font-bold text-xs">+</button>
                            </div>
                            <button onclick="removeFromCart(${item.id})" class="text-gray-400 hover:text-red-500 text-xs transition-colors">
                                <i class="fa-solid fa-trash-can"></i>
                            </button>
                        </div>
                    </div>
                `;
                list.appendChild(div);
            });

            document.getElementById('cartSubtotal').innerText = `₹${subtotal.toLocaleString('en-IN')}`;
            document.getElementById('cartTotal').innerText = `₹${subtotal.toLocaleString('en-IN')}`;
        }

        function toggleCartDrawer(open) {
            const drawer = document.getElementById('cartDrawer');
            if (open) {
                renderCartItems();
                drawer.classList.remove('hidden');
            } else {
                drawer.classList.add('hidden');
            }
        }

        // Checkout & Payment Workflow
        function openCheckout() {
            if (cart.length === 0) return;
            toggleCartDrawer(false);
            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            document.getElementById('checkoutTotalAmount').innerText = `₹${subtotal.toLocaleString('en-IN')}`;
            document.getElementById('checkoutModal').classList.remove('hidden');
        }

        function closeCheckout() {
            document.getElementById('checkoutModal').classList.add('hidden');
        }

        function togglePaymentFields(method) {
            document.getElementById('upiFields').classList.toggle('hidden', method !== 'UPI');
            document.getElementById('cardFields').classList.toggle('hidden', method !== 'Card');
            document.getElementById('codFields').classList.toggle('hidden', method !== 'COD');
        }

        function handleCheckoutSubmit(event) {
            event.preventDefault();
            const name = document.getElementById('custName').value;
            const paymentMethod = document.querySelector('input[name="paymentMethod"]:checked').value;
            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);

            closeCheckout();

            // Populate confirmation
            document.getElementById('confirmOrderId').innerText = `#LUM-${Math.floor(10000 + Math.random() * 90000)}`;
            document.getElementById('confirmCustomerName').innerText = name;
            document.getElementById('confirmPaymentMode').innerText = paymentMethod;
            document.getElementById('confirmTotal').innerText = `₹${subtotal.toLocaleString('en-IN')}`;

            document.getElementById('confirmationModal').classList.remove('hidden');
        }

        function finishOrder() {
            cart = [];
            updateCartBadge();
            document.getElementById('confirmationModal').classList.add('hidden');
            document.getElementById('checkoutForm').reset();
            window.scrollTo({ top: 0, behavior: 'smooth' });
            showToast('Order placed successfully!');
        }

        // Toast Notification System
        function showToast(message) {
            const toast = document.getElementById('toast');
            document.getElementById('toastMsg').innerText = message;
            toast.classList.remove('translate-y-20', 'opacity-0');
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }
    </script>
</body>
</html>
