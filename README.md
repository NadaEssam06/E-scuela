
### **README.md**

```markdown
# Vue Student Management Dashboard

This is a responsive Vue 3 dashboard application designed to manage student data and provide a user-friendly interface for interaction. It includes structured routing, modular components, a contact form, and clean UI layouts using Tailwind CSS.

## Features

- Component-based architecture using Vue 3
- Student table with dynamic data rendering
- Sidebar and top navigation with route integration
- Contact form with input validation and feedback
- JSON-based local student data
- Not Found route for invalid pages

## Project Structure
```

project/
├── public/
│ ├── favicon.ico
│ └── index.html
├── src/
│ ├── assets/
│ │ ├── logo.png
│ │ └── notFound.svg
│ ├── components/
│ │ ├── AddButton.vue
│ │ ├── EditButton.vue
│ │ ├── aside.vue
│ │ ├── Contact.vue
│ │ ├── Footer.vue
│ │ ├── Home.vue
│ │ ├── navbar.vue
│ │ ├── NotFound.vue
│ │ ├── Student.vue
│ │ └── StudentTable.vue
│ ├── data/
│ │ └── students.json
│ ├── routes/
│ │ └── index.vue
│ ├── App.vue
│ └── main.js

````

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/NadaEssam06/E-scuela.git
   cd your-repo
````

2. Install dependencies:

   ```bash
   npm install
   ```

3. Run the development server:

   ```bash
   npm run dev
   ```

4. Open in browser:
   Navigate to `http://localhost:5173` (or as printed in your terminal)

## Technologies Used

- Vue 3 (Composition API)
- Vue Router
- Tailwind CSS
- JSON (for local data)
- Vite (for development/build tooling)

## Contact

If you'd like to contribute, report issues, or suggest features, feel free to open an issue or submit a pull request.

## License

This project is open-source and available under the MIT License.
