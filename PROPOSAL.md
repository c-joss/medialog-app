# Phase 5 Project Proposal — **MediaLog: Personal Collection Tracker**

## 1. Introduction

**Overview:**  
MediaLog is a full-stack web application that allows users to organize and manage their personal collections — such as books, movies, games, or music — in one elegant interface.

**Problem:**  
People who enjoy tracking collections often rely on spreadsheets or simple note-taking apps, which don’t provide visual appeal, categorization, or efficient data management. These methods make it difficult to browse, rearrange, or share collections easily.

**Proposed Solution:**  
MediaLog replaces the need for scattered manual tracking systems with a sleek, interactive platform. Users can create collection entries, assign categories and tags, add reviews and personal ratings, visually rearrange their gallery using drag-and-drop, and export the entire collection to Excel for backup or sharing.

**Benefits:**

- **Centralized Collection Management:** Keeps all hobbies in one place with images, ratings, and categories.
- **Enhanced User Interaction:** Allows drag-and-drop reordering and Excel exporting for advanced usability.
- **Visual Appeal:** Offers a clean, professional interface with smooth animations for a modern user experience.

---

## 2. Issue / Background

**Who it affects:**  
Individuals who want a better way to manage personal collections.

**Current limitations:**

- Manual tools like spreadsheets lack tagging, filtering, and visual sorting.
- Difficult to rearrange or browse items intuitively.
- No built-in export feature for data portability.

**Why it matters:**  
MediaLog addresses these gaps while demonstrating advanced technical skills through structured data modeling, React routing, API handling, and modern UI interactivity.

---

## 3. Proposed Solution

### Backend — Flask + SQLAlchemy

**Models**
| Model | Purpose | Key Fields |
|-------|----------|------------|
| `User` | Simulate user ownership | `id`, `username` |
| `Item` | Represents a hobby entry | `id`, `title`, `description`, `rating`, `review`, `image_url`, `category_id` |
| `Category` | Groups items by type | `id`, `name` |
| `Tag` | Flexible item labels | `id`, `name` |
| `item_tags` | Join table (many-to-many) | `item_id`, `tag_id` |

**Key Features**

- CRUD for `Item` (Create, Read, Update, Delete).
- Validations: required `title`, `category_id`, `rating` between 1–5.
- Error handling for invalid data and missing records.
- Excel export endpoint using **Pandas**.

---

### Frontend — React

**Routes**

1. `/` – Dashboard / Home
2. `/items` – All items view
3. `/items/:id` – Item detail (review + rating)
4. `/add` – Add / Edit item form
5. `/profile` – User summary of collections

**Key Features**

- `Interactive Collection Management`: Users can create, edit, delete, and organize collection items by category and tags.
- `Drag & Drop Reordering`: Built with dnd-kit, allowing users to visually rearrange their collection cards.
- `Export to Excel`: Backend functionality built with Pandas generates downloadable `.xlsx` files for data backup or sharing.
- `Personal Reviews & Ratings`: Optional section for users to add personal impressions or ratings for each item.
- `Modern UI & Animation`: Minimalist, responsive layout with optional motion effects powered by Framer Motion for a refined user experience.

---

### Libraries & Tools

| Purpose                  | Library / Tool                     | Description                                                                                          |
| ------------------------ | ---------------------------------- | ---------------------------------------------------------------------------------------------------- |
| **Frontend Framework**   | **React**                          | Core UI library for building the client interface.                                                   |
| **Routing**              | **React Router**                   | Manages navigation between pages (Home, Items, Add, Profile).                                        |
| **State Management**     | **useContext (React Hook)**        | Handles global state for current user and collection data.                                           |
| **Drag & Drop**          | **dnd-kit**                        | Modern React-first drag-and-drop toolkit for intuitive item reordering with accessible interactions. |
| **Animation (optional)** | **Framer Motion**                  | Adds subtle hover, fade, and drag transitions for a polished, dynamic UI.                            |
| **Backend Framework**    | **Flask**                          | Python web framework for API routes and server logic.                                                |
| **ORM / Database**       | **SQLAlchemy**                     | Manages relational data models and database connections.                                             |
| **Data Export**          | **Pandas**                         | Generates downloadable Excel (.xlsx) files of the user’s collection.                                 |
| **Styling**              | **Tailwind CSS** or **Custom CSS** | Ensures a minimalist, professional, and fully responsive design.                                     |

---

## 4. Experience / Qualifications

**Developer:** _Courtney Macgregor_

- 13 years in shipping and logistics; currently transitioning to software engineering.
- Completed coursework covering Flask, React, and SQLAlchemy, with practical experience deploying projects using Render.

---

## 6. Costs & Benefits

| Type         | Details                                                                                                                   |
| ------------ | ------------------------------------------------------------------------------------------------------------------------- |
| **Costs**    | Free open-source tools; hosting via Render (no additional expenses).                                                      |
| **Benefits** | Showcases full-stack proficiency with enhanced functionality that reflects real-world, professional application behavior. |

---

## 8. How **MediaLog** Meets Phase 5 Project Requirements

| Requirement                           | Implementation                                                                  |
| ------------------------------------- | ------------------------------------------------------------------------------- |
| **Flask + SQLAlchemy backend**        | Flask handles API routes and database logic using SQLAlchemy ORM.               |
| **4+ Models**                         | `User`, `Item`, `Category`, `Tag`, and `item_tags` join table.                  |
| **Many-to-Many Relationship**         | Implemented between `Item` and `Tag` through `item_tags`.                       |
| **Full CRUD on one model**            | Full create, read, update, delete operations on `Item`.                         |
| **Validations & Error Handling**      | Title, category, and rating validations; backend returns clear error messages.  |
| **5+ Client-side Routes**             | Home, Items, Item Detail, Add/Edit Item, Profile.                               |
| **useContext or Redux**               | useContext manages global state for user and collection data.                   |
| **Something New (beyond curriculum)** | 1) Drag-and-drop interface using dnd-kit. 2) Excel export feature using Pandas. |
| **Professional Design**               | Clean UI, responsive layout, subtle animations.                                 |

---

## 7. Resources

- **ERD (PDF):**  
  [medialog.drawio (1).pdf](<./medialog.drawio%20(1).pdf>)

- **Wireframes (PDF):**  
  [Medialog Wireframes.pdf](./Medialog%20Wireframes.pdf)

- **Normalization Worksheet (Excel):**  
  [Medialog Normalisation.xlsx](./Medialog%20Normalisation.xlsx)

  ***

## 8. Conclusion

MediaLog is a feature-rich yet manageable project that fulfills all Phase 5 criteria while showcasing creativity and technical precision. It combines practical functionality (CRUD, validations, relationships) with modern UX touches like drag-and-drop and Excel export, resulting in a polished, portfolio-ready capstone.
