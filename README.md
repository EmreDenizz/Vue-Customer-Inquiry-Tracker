# Customer Inquiry Tracker

A Vue.js application for tracking customer inquiries. This application allows you to add, view, and manage customer inquiries with priority levels.

## Features
- Add new customer inquiries with name, details, and priority level
- View list of all inquiries
- Delete existing inquiries
- Priority levels: Low, Medium, High
- Responsive design with modern UI

## Screenshot
<img src="public/SS.png" alt="Customer Inquiry Tracker Screenshot" width="400">

## Current State
The application currently stores data in memory. Data will be lost upon page refresh or browser closure.

## Project setup
```
npm install
```

## Build Options

### Vue CLI (Default)
```
npm run serve     # Development
npm run build     # Production build
```

### Vite (Faster builds)
```
npm run dev:vite    # Development with Vite
npm run build:vite  # Production build with Vite
npm run preview     # Preview production build
```

### Lints and fixes files
```
npm run lint
```

## Future Improvements
- Implement persistent data storage
- Add search and filter functionality
- Add status tracking for inquiries
- Add timestamps for inquiries
- Add user authentication
