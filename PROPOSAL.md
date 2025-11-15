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

**Core Features**

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
- `Drag & Drop Reordering`: Built with React Beautiful DND, allowing users to visually rearrange their collection cards.
- `Export to Excel`: Backend functionality built with Pandas generates downloadable `.xlsx` files for data backup or sharing.
- `Personal Reviews & Ratings`: Optional section for users to add personal impressions or ratings for each item.
- `Modern UI & Animation`: Minimalist, responsive layout with optional motion effects powered by Framer Motion for a refined user experience.

---
