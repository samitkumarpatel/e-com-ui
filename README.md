# E-Commerce Frontend Single Page Application

A responsive e-commerce frontend built with Vue 3, Pinia, Vuetify (Material Design), and vanilla JavaScript in a single HTML file.

## Features

### 🛍️ Core Functionality
- **Product Catalog**: Browse products with images, prices, ratings, and stock information
- **Categories**: Filter products by categories (Electronics, Jewelery, Men's/Women's Clothing)
- **Search**: Real-time search functionality to find products quickly
- **Shopping Cart**: Add/remove products, adjust quantities, view total
- **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices

### 🎨 UI/UX Features
- **Material Design**: Clean, modern interface using Vuetify components
- **Product Cards**: Hover effects, discount badges, and stock indicators
- **Cart Management**: Side drawer with quantity controls and item removal
- **Loading States**: Progress indicators for better user experience
- **Notifications**: Toast messages for user actions
- **Empty States**: Friendly messages when cart or search results are empty

### 🛠️ Technical Features
- **Vue 3 Composition API**: Modern reactive framework
- **Pinia Store**: Centralized state management for products and cart
- **API Integration**: Fetches real data from FakeStore API
- **Responsive Grid**: Adaptive layout for different screen sizes
- **Local Storage**: Cart persists across browser sessions (can be added)

## How to Use

### 1. Open the Application
Simply open `index.html` in any modern web browser. No build process or server required!

### 2. Browse Products
- View all products on the main page
- Use category chips to filter by product type
- Use the search bar to find specific products
- Products show original price, discounted price (if applicable), and stock levels

### 3. Shopping Cart
- Click "Add to Cart" on any product card
- Cart icon in the header shows item count
- Click cart icon to open the cart drawer
- In cart: adjust quantities with +/- buttons, remove items, see total

### 4. Categories
- Click category chips to filter products
- "All Products" shows all available items
- Categories are dynamically loaded from the API

## API Integration

The application uses the [FakeStore API](https://fakestoreapi.com/) for demonstration:
- **Products**: `https://fakestoreapi.com/products`
- **Categories**: `https://fakestoreapi.com/products/categories`

### To Use Your Own API:
1. Change the `API_BASE_URL` constant in the script section
2. Modify the `fetchProducts()` and `fetchCategories()` functions to match your API structure
3. Update the product data mapping to match your backend response

## File Structure

```
e-com-ui/
├── index.html          # Complete single-page application
└── README.md          # This documentation
```

## Technologies Used

- **Vue 3**: Progressive JavaScript framework
- **Pinia**: Official state management for Vue
- **Vuetify 3**: Vue Material Design component framework
- **Material Design Icons**: Comprehensive icon library
- **FakeStore API**: Demo e-commerce API

## Browser Compatibility

- Chrome 60+
- Firefox 60+
- Safari 12+
- Edge 79+

## Features Implementation Details

### Pinia Store Structure
```javascript
// State
products: []        // All products from API
categories: []      // Product categories
cartItems: []       // Items in shopping cart
loading: boolean    // Loading state

// Getters
cartItemsCount      // Total items in cart
cartTotal          // Total cart value with discounts

// Actions
fetchProducts()     // Get products from API
fetchCategories()   // Get categories from API
addToCart()        // Add product to cart
removeFromCart()   // Remove product from cart
updateCartItemQuantity() // Change item quantity
```

### Component Architecture
- **Main App**: Handles routing between product view and cart
- **Product Grid**: Displays products with filtering and search
- **Product Card**: Individual product display with add to cart
- **Cart Drawer**: Side panel for cart management
- **Category Filter**: Chip-based category selection

## Customization

### Styling
- Modify the `<style>` section for custom CSS
- Change Vuetify theme colors in the Vue app configuration
- Adjust responsive breakpoints in the grid system

### Adding Features
- **User Authentication**: Add login/signup functionality
- **Product Details**: Create detailed product view pages
- **Checkout Process**: Implement payment integration
- **Order History**: Add user order tracking
- **Wishlist**: Implement product favorites
- **Reviews**: Add product rating and review system

## Development Notes

- The application is fully self-contained in a single HTML file
- All dependencies are loaded via CDN
- No build process required - just open in browser
- State is managed through Pinia store
- Responsive design adapts to all screen sizes
- API calls are handled with native fetch API

## Performance Considerations

- Images are lazy-loaded by Vuetify
- API calls are cached in the store
- Computed properties optimize filtering and calculations
- Minimal re-renders with Vue 3's reactivity system

## Future Enhancements

1. **Persistence**: Save cart to localStorage
2. **Sorting**: Add price/rating sort options
3. **Pagination**: Handle large product catalogs
4. **Filters**: Advanced filtering by price, rating, etc.
5. **PWA**: Convert to Progressive Web App
6. **Testing**: Add unit and integration tests
