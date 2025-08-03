# Omi - Give and Receive Freely (Free Tier Edition)

![Omi Logo](https://placehold.co/600x300/A8D5BA/333333?text=Omi)

## Project Overview

Omi is a community-driven platform dedicated to reducing waste and fostering a culture of giving. It allows users to easily give away items they no longer need to others in their local community. The platform incorporates a gamification system with points and regional rankings to encourage participation and recognize generous members.

The core principle of Omi is to make the process of giving and receiving free items simple, safe, and enjoyable, using a tech stack that can be deployed entirely for free.

---

## Functional Specifications

### 1. User Management
- **Authentication:** Users can sign up using email/password or OAuth (Google, Facebook), managed by **Supabase Auth**.
- **User Profiles:** Each user has a public profile displaying their username, region, total points, and current rank.
- **Profile Management:** Users can update their profile information.

### 2. Item Listings
- **Create Listing:** Users can create a new post for an item with a title, description, photos, category, and pickup location.
- **Manage Listings:** Users can view, edit, delete, and mark their listings as "taken".
- **Browse & Search:** A localized feed with search and filter capabilities.

### 3. Communication
- **Integrated Messaging:** A secure, real-time messaging system. For a free-tier solution, this can be implemented using Supabase's Realtime functionality with PostgreSQL tables.
- **Conversation Threads:** Messages are organized by item.
- **Safety:** No personal contact information is exposed.

### 4. Gamification & Ranking
- **Points System:** Users earn points and badges for giving away items.
- **Leaderboards:** Regional rankings display top givers.

---

## Technical Specifications (Free Tier Architecture)

This project is a full-stack application written entirely in Rust, designed to run on services with generous free tiers.

### 1. Backend Services (Database, Auth, Storage)
- **Platform:** **Supabase**
- **Database:** A free **PostgreSQL** instance provided by Supabase. The schema remains the same.
- **Database Driver:** **SQLx** is used in the Rust backend to connect to the Supabase database.
- **Authentication:** Handled by **Supabase Auth**, which manages user sign-up, login, and JWT generation.
- **Image Storage:** Handled by **Supabase Storage**, which provides an S3-compatible interface for user-uploaded photos.

### 2. Backend Hosting
- **Language:** **Rust** (Stable toolchain)
- **Web Framework:** **Actix Web**
- **Deployment Platform:** **Shuttle**
- **Description:** Shuttle is a Rust-native cloud platform with a "forever-free" tier. It allows for deploying the Actix Web backend with a single command, without needing Dockerfiles.

### 3. Frontend
- **Language:** **Rust** compiled to **WebAssembly (Wasm)**.
- **Framework:** **Yew** - A modern Rust framework for creating multi-threaded frontend web apps.
- **Styling:** **Tailwind CSS**
- **Bundler:** **Trunk**
- **Deployment Platform:** **Cloudflare Pages**
- **Description:** Cloudflare Pages offers free, high-performance hosting for static sites (which is what a compiled Yew app is). It includes a global CDN, making the app fast worldwide.
