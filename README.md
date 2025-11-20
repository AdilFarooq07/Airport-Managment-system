# Airport Management System

A complete frontend-only Airport Management System built with React.js, featuring user and ticket CRUD operations, flight viewing, and booking interlinking. All state management is handled through React Context API with localStorage persistence.

**Assigned by:** CEO & Founder — Usama Aslam  
**Organization:** U Devs  
**Project Type:** Frontend-Only Task

---

## 🚀 Features

### Core Functionality
- ✅ **Splash Screen** - Visually appealing splash screen with automatic routing
- ✅ **Authentication** - Frontend-only login and registration system
- ✅ **User CRUD** - Complete Create, Read, Update, Delete operations for users
- ✅ **Ticket CRUD** - Full management of flight tickets/flights
- ✅ **Booking System** - Link users to tickets (bookings)
- ✅ **Flight View** - Display all flights with details (time, gate, status)
- ✅ **Dashboard** - Overview with statistics and recent activities
- ✅ **Context API** - All state managed through Context (no prop drilling)
- ✅ **localStorage** - Data persistence across page refreshes
- ✅ **Responsive Design** - Works seamlessly on mobile and desktop
- ✅ **Form Validation** - Comprehensive validation with error messages
- ✅ **Confirmation Modals** - Safe delete/edit operations

---

## 🛠️ Technology Stack

- **React.js** (v19.2.0) - UI library
- **React Router** (v7.9.6) - Navigation and routing
- **Bootstrap 5** (v5.3.8) - Styling framework
- **React Icons** (v5.5.0) - Icon library
- **Vite** (v7.2.4) - Build tool and dev server
- **Context API** - State management (no Redux/other libraries)
- **localStorage** - Data persistence

---

## 📁 Folder Structure

```
airport-management/
├── public/
│   └── vite.svg
├── src/
│   ├── components/
│   │   ├── common/
│   │   │   ├── PageHeader.jsx      # Reusable page header component
│   │   │   └── StatCard.jsx        # Statistics card component
│   │   ├── layout/
│   │   │   └── AppLayout.jsx       # Main app layout with sidebar
│   │   └── ui/
│   │       ├── ConfirmDialog.jsx   # Confirmation modal for delete actions
│   │       ├── FormInput.jsx       # Reusable form input component
│   │       └── Modal.jsx            # Reusable modal component
│   ├── context/
│   │   ├── AppProviders.jsx        # Combines all context providers
│   │   ├── AuthContext.jsx         # Authentication state management
│   │   ├── BookingContext.jsx      # Booking/linking state management
│   │   ├── TicketContext.jsx       # Ticket/flight state management
│   │   └── UserContext.jsx         # User state management
│   ├── hooks/
│   │   ├── useAuth.js              # Custom hook for authentication
│   │   ├── useBookings.js          # Custom hook for bookings
│   │   ├── useTickets.js            # Custom hook for tickets
│   │   └── useUsers.js              # Custom hook for users
│   ├── pages/
│   │   ├── Bookings.jsx            # Booking management page
│   │   ├── Dashboard.jsx            # Main dashboard with stats
│   │   ├── Flights.jsx              # Flight viewing page
│   │   ├── Login.jsx                # Login page
│   │   ├── Register.jsx             # Registration page
│   │   ├── Splash.jsx               # Splash screen
│   │   ├── Tickets.jsx              # Ticket CRUD page
│   │   └── Users.jsx                # User CRUD page
│   ├── routes/
│   │   ├── AppRouter.jsx            # Main router configuration
│   │   └── ProtectedRoute.jsx       # Route protection wrapper
│   ├── styles/
│   │   └── theme.css                # Custom theme styles
│   ├── utils/
│   │   ├── formatters.js            # Date and currency formatters
│   │   └── generateId.js            # ID generation utility
│   ├── App.css                      # Global app styles
│   ├── App.jsx                      # Root app component
│   ├── index.css                    # Base styles and imports
│   └── main.jsx                     # Application entry point
├── .eslintrc.cjs                    # ESLint configuration
├── index.html                       # HTML template
├── package.json                     # Dependencies and scripts
├── vite.config.js                   # Vite configuration
└── README.md                        # This file
```

---

## 🚦 Getting Started

### Prerequisites

- **Node.js** (v16 or higher recommended)
- **npm** (comes with Node.js) or **yarn**

### Installation

1. **Navigate to the project directory:**
   ```bash
   cd airport-management
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

4. **Open your browser:**
   - The app will be available at `http://localhost:5173` (or the port shown in terminal)
   - Vite will automatically open the browser

### Build for Production

```bash
npm run build
```

The production build will be in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
```

---

## 📖 Usage Guide

### Initial Setup

1. **First Launch:**
   - The app starts with a splash screen
   - After 2.2 seconds, you'll be redirected to login (if not authenticated)

2. **Default Users:**
   The app comes with 3 seed users:
   - **Ayesha Khan** (Administrator)
     - Email: `ayesha.khan@udev-hub.com`
     - Password: `admin123`
   - **Hamza Usman** (Operations)
     - Email: `hamza.usman@udev-hub.com`
     - Password: `ops@airport`
   - **Sara Ali** (Passenger)
     - Email: `sara.ali@udev-hub.com`
     - Password: `flysara`

3. **Register New User:**
   - Click "Create an account" on the login page
   - Fill in all required fields
   - You'll be automatically logged in after registration

### Features Walkthrough

#### Dashboard
- View statistics: Active Users, Available Flights, Live Bookings, Average Ticket Value
- See upcoming departures
- View your personal bookings
- Monitor latest booking activities

#### Users Management
- **Add User:** Click "Add user" button
- **Edit User:** Click "Edit" button on any user row
- **Delete User:** Click "Delete" button (with confirmation)
- **Search:** Use the search bar to filter by name, email, or role
- **View Bookings:** See how many bookings each user has

#### Tickets Management
- **Add Ticket:** Click "Add ticket" button
- **Edit Ticket:** Click "Edit" button on any ticket row
- **Delete Ticket:** Click "Delete" button (with confirmation)
- **Search:** Filter by flight number, route, or status
- **View Bookings:** See how many users booked each ticket

#### Flights View
- View all available flights in card layout
- Filter by status: All, On Time, Boarding, Delayed, Cancelled
- See which flights you've booked (highlighted)
- View flight details: route, schedule, gate, price, status

#### Bookings Console
- **Create Booking:** Link a user to a ticket/flight
- **View All Bookings:** See all active user-ticket links
- **Cancel Booking:** Remove a booking link
- Real-time updates from Context

---

## 🎯 Context API Usage

This project uses **React Context API exclusively** for state management. No prop drilling is used anywhere.

### Context Architecture

#### 1. **AuthContext** (`src/context/AuthContext.jsx`)
Manages authentication state:
- `currentUser` - Currently logged-in user (without password)
- `isAuthenticated` - Boolean authentication status
- `login(email, password)` - Login function
- `register(payload)` - Registration function
- `logout()` - Logout function
- **Storage:** `ams_current_user` in localStorage

#### 2. **UserContext** (`src/context/UserContext.jsx`)
Manages all user data:
- `users` - Array of all users
- `addUser(payload)` - Create new user
- `updateUser(userId, updates)` - Update existing user
- `removeUser(userId)` - Delete user
- **Storage:** `ams_users` in localStorage
- **Seed Data:** 3 default users included

#### 3. **TicketContext** (`src/context/TicketContext.jsx`)
Manages all ticket/flight data:
- `tickets` - Array of all tickets
- `addTicket(payload)` - Create new ticket
- `updateTicket(ticketId, updates)` - Update existing ticket
- `removeTicket(ticketId)` - Delete ticket
- **Storage:** `ams_tickets` in localStorage
- **Seed Data:** 3 default tickets included

#### 4. **BookingContext** (`src/context/BookingContext.jsx`)
Manages user-ticket linking:
- `bookings` - Array of all bookings
- `bookTicket(userId, ticketId)` - Link user to ticket
- `cancelBooking(bookingId)` - Remove booking link
- `getBookingsByUser(userId)` - Get all bookings for a user
- `getBookingsByTicket(ticketId)` - Get all bookings for a ticket
- `removeBookingsByUser(userId)` - Remove all bookings when user is deleted
- `removeBookingsByTicket(ticketId)` - Remove all bookings when ticket is deleted
- **Storage:** `ams_bookings` in localStorage
- **Seed Data:** 1 default booking included

### Custom Hooks

Each context has a corresponding custom hook for easy access:

- `useAuth()` - Access authentication state and functions
- `useUsers()` - Access user data and CRUD operations
- `useTickets()` - Access ticket data and CRUD operations
- `useBookings()` - Access booking data and operations

**Example Usage:**
```jsx
import { useAuth } from '../hooks/useAuth';
import { useUsers } from '../hooks/useUsers';

const MyComponent = () => {
  const { currentUser, logout } = useAuth();
  const { users, addUser } = useUsers();
  
  // Use the data and functions...
};
```

### Provider Hierarchy

All contexts are wrapped in `AppProviders` component:

```jsx
<UserProvider>
  <TicketProvider>
    <BookingProvider>
      <AuthProvider>
        {children}
      </AuthProvider>
    </BookingProvider>
  </TicketProvider>
</UserProvider>
```

**Order matters:** UserProvider and TicketProvider must be above BookingProvider and AuthProvider because:
- BookingProvider needs access to users and tickets
- AuthProvider needs access to users for login/register

---

## 🎨 Styling Framework: Bootstrap 5

This project uses **Bootstrap 5.3.8** for styling.

### Why Bootstrap?
- ✅ Comprehensive component library
- ✅ Responsive grid system
- ✅ Built-in utility classes
- ✅ Consistent design system
- ✅ Well-documented and widely used

### Custom Styling

Additional custom styles are in:
- `src/styles/theme.css` - Custom theme variables and component styles
- `src/App.css` - Global app-specific styles
- `src/index.css` - Base styles and font imports

### Key Custom Styles

- **Color Scheme:** Blue primary (`#1d4ed8`), dark backgrounds
- **Status Badges:** Color-coded flight statuses (On Time, Boarding, Delayed, Cancelled)
- **Sidebar Navigation:** Custom styled with active states
- **Modals:** Custom backdrop and rounded corners
- **Splash Screen:** Gradient background with animation
- **Auth Pages:** Gradient backgrounds with centered cards

### Responsive Design

- **Mobile:** Sidebar becomes horizontal, stacked layouts
- **Tablet:** Optimized card layouts, flexible grids
- **Desktop:** Full sidebar, multi-column layouts

---

## 🔒 Route Protection

Protected routes are implemented using `ProtectedRoute` component:

- **Public Routes:** `/`, `/login`, `/register`
- **Protected Routes:** `/dashboard`, `/users`, `/tickets`, `/flights`, `/bookings`
- **Auto-redirect:** Unauthenticated users are redirected to login
- **State preservation:** Original destination is saved for redirect after login

---

## 💾 Data Persistence

All data is stored in **localStorage** with the following keys:

- `ams_current_user` - Current authenticated user
- `ams_users` - All users
- `ams_tickets` - All tickets/flights
- `ams_bookings` - All booking links

**Features:**
- Automatic save on every state change
- Automatic load on app initialization
- Seed data if localStorage is empty
- Error handling for corrupted data

---

## ✅ Validation & Error Handling

### Form Validation
- **Required fields** - All forms validate required inputs
- **Email format** - Email validation on login/register
- **Password matching** - Confirm password validation on register
- **Real-time feedback** - Errors clear as user types
- **Visual indicators** - Invalid fields highlighted in red

### Error Messages
- Clear, user-friendly error messages
- Context-specific error handling
- Try-catch blocks for all async operations
- Fallback values for missing data

### Confirmation Dialogs
- Delete operations require confirmation
- Clear messaging about what will be deleted
- Cancellable actions

---

## 🧪 Testing the Application

### Manual Testing Checklist

1. **Splash Screen**
   - [ ] Appears on initial load
   - [ ] Redirects to login if not authenticated
   - [ ] Redirects to dashboard if authenticated

2. **Authentication**
   - [ ] Login with valid credentials works
   - [ ] Login with invalid credentials shows error
   - [ ] Registration creates new user
   - [ ] Registration with existing email shows error
   - [ ] Logout clears session

3. **User CRUD**
   - [ ] Add new user
   - [ ] Edit existing user
   - [ ] Delete user (with confirmation)
   - [ ] Search filters users correctly
   - [ ] Data persists after refresh

4. **Ticket CRUD**
   - [ ] Add new ticket
   - [ ] Edit existing ticket
   - [ ] Delete ticket (with confirmation)
   - [ ] Search filters tickets correctly
   - [ ] Data persists after refresh

5. **Bookings**
   - [ ] Link user to ticket
   - [ ] Prevent duplicate bookings
   - [ ] Cancel booking
   - [ ] View bookings by user
   - [ ] View bookings by ticket
   - [ ] Bookings removed when user/ticket deleted

6. **Flights View**
   - [ ] All flights displayed
   - [ ] Status filter works
   - [ ] Booked flights highlighted
   - [ ] Responsive card layout

7. **Responsive Design**
   - [ ] Works on mobile (< 576px)
   - [ ] Works on tablet (576px - 991px)
   - [ ] Works on desktop (> 991px)

---

## 📝 Code Quality

- ✅ **Modular Components** - Reusable UI components
- ✅ **Custom Hooks** - Clean context access
- ✅ **Error Boundaries** - Try-catch blocks where needed
- ✅ **Comments** - Well-documented code
- ✅ **Consistent Naming** - Clear, descriptive names
- ✅ **ESLint** - Code linting configured

---

## 🐛 Troubleshooting

### Issue: App won't start
**Solution:** 
- Ensure Node.js v16+ is installed
- Run `npm install` to install dependencies
- Check for port conflicts (change port in vite.config.js if needed)

### Issue: Data not persisting
**Solution:**
- Check browser localStorage (DevTools > Application > Local Storage)
- Clear localStorage and refresh (seed data will reload)
- Check browser console for errors

### Issue: Styles not loading
**Solution:**
- Ensure Bootstrap is installed: `npm install bootstrap`
- Check that `main.jsx` imports Bootstrap CSS
- Clear browser cache

### Issue: Routing not working
**Solution:**
- Ensure React Router is installed: `npm install react-router-dom`
- Check that routes are properly configured in `AppRouter.jsx`
- Verify BrowserRouter is wrapping the app

---

## 📧 Contact Information

**Founder & CEO:** Usama Aslam  
- Email: ceo@usama-aslam.com

**Senior Project Manager:** Minahil Hasan  
- Email: project.manager@minahil-hasan.info

**Official Email:** udevsofficial25@gmail.com

**Websites:**
- www.udev-hub.com
- www.usama-aslam.com
- www.minahil-hasan.info

---

## 📄 License

This project is created for U Devs as a frontend-only task assignment.

---

## 🎉 Acknowledgments

- Built with React.js and Vite
- Styled with Bootstrap 5
- Icons from React Icons
- Font: Inter (Google Fonts)

---

**Generated on:** 2025-11-04  
**Project Status:** ✅ Complete and Ready for Review
