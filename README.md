# Taskify 📝

Taskify is a simple, lightweight, file-based task management and note-taking application built with Node.js and Express. It allows users to create, view, and rename tasks or notes directly on the server's file system. The application features a clean, modern interface styled with Tailwind CSS.

## Features ✨

* [cite_start]**Create Tasks**: Quickly create new tasks with a title and detailed description[cite: 4]. The title is used as the filename (with spaces removed), and the details are saved as the file's content.
* [cite_start]**View All Tasks**: The homepage displays all the tasks currently saved in the `/files` directory[cite: 4, 7].
* [cite_start]**Read Task Details**: Click "Read More" on any task card to view its full content on a dedicated page[cite: 3, 6].
* **Edit Filename**: Easily update the title of a task. [cite_start]The application renames the underlying file on the server[cite: 1, 2].
* [cite_start]**Minimalist UI**: A clean and responsive user interface built with Tailwind CSS for a seamless user experience on all devices[cite: 1, 3, 4].

## Technology Stack

* **Backend**: Node.js, Express.js
* **Frontend**: EJS (Embedded JavaScript templates), Tailwind CSS
* **Core Modules**: Node.js `fs` (File System) for file operations, `path` for directory management.

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine.

### Prerequisites

You need to have Node.js and npm (Node Package Manager) installed on your system.
* [Node.js](https://nodejs.org/)

### Installation

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/kadiamyeshwanth/taskify.git](https://github.com/kadiamyeshwanth/taskify.git)
    ```

2.  **Navigate to the project directory:**
    ```sh
    cd taskify
    ```

3.  **Install the dependencies:**
    ```sh
    npm install
    ```

4.  **Create the `files` directory:**
    The application reads and writes from a `./files` directory. Create it in the root of the project.
    ```sh
    mkdir files
    ```

5.  **Run the application:**
    ```sh
    node index.js
    ```
    The server will start, and you can access the application at `http://localhost:3000`.

## How It Works

The application uses the Node.js `fs` module to manage tasks as `.txt` files on the server.

* [cite_start]**Creating a task**: A form submission triggers a `POST` request to `/create`, which uses `fs.writeFile()` to save a new file[cite: 4, 5].
* [cite_start]**Reading a task**: Navigating to `/file/:filename` triggers a `GET` request, which uses `fs.readFile()` to fetch and display the file's content[cite: 3, 6].
* [cite_start]**Renaming a task**: Submitting the edit form sends a `POST` request to `/edit`, which uses `fs.rename()` to update the filename[cite: 1, 2].
