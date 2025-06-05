# 🚀 VectorShift Frontend Technical Assessment

This repository contains the solution to the **VectorShift Frontend Technical Assessment**. The project demonstrates a full-stack application with a **React**-based frontend and a **FastAPI** backend. It features a flexible node-based pipeline editor, styled interface, dynamic node behavior, and backend integration for DAG validation.

---

## 📁 Project Structure

```
/
├── frontend/   # React application
└── backend/    # FastAPI server
```

---

## ⚙️ Getting Started

### 1. **Frontend Setup**

```bash
cd frontend
npm install
npm start
```

- Runs the app on: [http://localhost:3000](http://localhost:3000)

### 2. **Backend Setup**

```bash
cd backend
uvicorn main:app --reload
```

- Runs the server on: [http://localhost:8000](http://localhost:8000)

---

## 🧩 Features

### Part 1: Node Abstraction

A reusable and modular node abstraction system has been developed to enable fast creation of new node types. This system supports:

- Custom **input** and **output** handles
- Configurable fields like text inputs and dropdowns
- Shared UI components across nodes

#### ✅ Node Types Implemented:

- **Checkbox Node**
- **Color Picker Node**
- **Input Node**
- **String Concatenation Node**
- **Multiplier Node**

---

### Part 2: Styling & UI/UX

The application uses **TailwindCSS** and **NextUI** to provide a modern, minimal, and responsive UI.

#### 🖌️ Key Design Elements:

- Smooth drag-and-drop interface
- Responsive node resizing
- Visual cues for connections and interactions
- Hover and transition effects for better UX

---

### Part 3: Text Node Enhancements

The **Text Node** was enhanced with:

1. **Dynamic Resizing** – Adjusts size based on input length.
2. **Variable Detection** – Parses `{{variable}}` syntax and automatically generates corresponding input handles for data linking.

---

### Part 4: Backend Integration

On pipeline submission, the frontend sends node and edge data to the FastAPI backend, which:

- Counts nodes and edges
- Checks for **DAG (Directed Acyclic Graph)** structure using **NetworkX**
- Sends results back to the frontend for display via toast notifications

#### 🔁 API Endpoint

```
POST /pipelines/parse
```

#### 📤 Sample Request

```json
{
  "nodes": [...],
  "edges": [...]
}
```

#### 📥 Sample Response

```json
{
  "num_nodes": 5,
  "num_edges": 4,
  "is_dag": true
}
```

---

## 🛠️ Technologies Used

### Frontend

- **React**
- **React Flow**
- **Zustand** (state management)
- **TailwindCSS**
- **NextUI**
- **React Toastify** (notifications)

### Backend

- **FastAPI**
- **NetworkX**

---

## 🚧 Future Improvements

- ➕ Introduce additional customizable node types
- ✅ Add input validation across node fields
- 🛡️ Enhance error handling during pipeline submission
- 🎨 Improve overall styling and UX polish

---

## 📌 Conclusion

This project showcases a modular, visually appealing, and technically sound implementation of a pipeline editor with DAG validation and modern frontend/backed practices. It serves as a flexible base for building more advanced visual programming tools.
