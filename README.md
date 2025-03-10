<p align="center">
  <a href="https://docs.basted.ru/">
    <img src="https://raw.githubusercontent.com/b1sted/docs/main/.github/assets/logo.webp" width="160" alt="downwardspiral">
  </a>
  <br>
    downwardspiral
  <br>
</p>

<p align="center">
  <strong>
    A comprehensive and user-friendly C programming documentation built with 
    <a href="https://www.mkdocs.org/">MkDocs</a> and <a href="https://github.com/squidfunk/mkdocs-material/">Material for MkDocs</a>
  </strong>
</p>

<h2></h2>

<p align="center">
  <a href="https://github.com/b1sted/docs/actions"><img
    src="https://github.com/b1sted/docs/actions/workflows/build.yml/badge.svg?branch=main"
    alt="Build"
  /></a>
  <a href="https://docs.basted.ru"><img
    src="https://img.shields.io/website?url=https%3A%2F%2Fdocs.basted.ru"
    alt="Website Status"
  /></a>
  <a href="https://github.com/b1sted/docs/blob/main/LICENSE"><img
    src="https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg"
    alt="License: CC BY-NC 4.0"
  /></a>
</p>

<p align="center">
  <a href="https://docs.basted.ru">
    <img src="https://raw.githubusercontent.com/b1sted/docs/main/.github/assets/screenshot.png" width="700" />
  </a>
</p>

<p align="center">
  <a href="#introduction">Introduction</a> •
  <a href="#key-features">Key Features</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#technologies-used">Technologies Used</a> •
  <a href="#performance-metrics">Performance Metrics</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#license">License</a> •
  <a href="#contact">Contact</a>
</p>

<h2></h2>

## Introduction

Welcome to the documentation for docs.basted.ru! This site hosts comprehensive lecture notes for learning C programming, with a focus on both foundational topics and advanced concepts. Whether you're new to C or looking to deepen your understanding, you'll find detailed explanations, examples, and real-world applications.

The documentation is built using MkDocs with the Material for MkDocs theme, ensuring a responsive, mobile-friendly experience that is easy to navigate. The site is fully open-source and free to use, hosted on GitHub Pages for reliable and fast access.

## Key Features

- Structured Learning Path: From basic syntax to advanced topics like pointers, memory management, and system programming.
- Clear Explanations & Code Examples: Designed for clarity, with practical examples to reinforce learning.
- Responsive Design: Optimized for all devices—desktops, tablets, and smartphones.
- Easy Navigation: A well-organized sidebar and search functionality to help you quickly find the information you need.
- Free & Open Source: Access the content anytime and contribute to improving it.

## Getting Started

To begin using the documentation, simply visit the site: [docs.basted.ru](https://docs.basted.ru). Navigate through the Table of Contents in the sidebar or use the search functionality to explore topics.

Below is the updated section that includes the Performance Metrics table along with the Local Setup instructions and steps to create a Python virtual environment:

### Local Setup

To set up the documentation locally, follow these steps:

1. **Clone the Repository:**

   ``` bash
   git clone https://github.com/b1sted/docs.git
   ```

2. **Create and Activate a Python Virtual Environment:**

   - **On macOS/Linux:**

     ``` bash
     python3 -m venv .venv
     source .venv/bin/activate
     ```

   - **On Windows:**

     ``` bash
     python -m venv .venv
     .\.venv\Scripts\activate
     ```

3. **Install Dependencies:**

   Ensure you have Python 3.9+ installed, then run:

   ``` bash
   pip install -r requirements.txt
   ```

4. **Start Local Server:**

   ``` bash
   mkdocs serve
   ```

   This will start a local development server at [http://127.0.0.1:8000](http://127.0.0.1:8000).

## Technologies Used

- MkDocs: A fast, simple static site generator.
- Material for MkDocs: A visually appealing theme for MkDocs, enhancing the user experience.
- GitHub Pages: Free and reliable hosting for the documentation.
- Markdown: Lightweight markup language used for writing the lecture notes.

## Performance Metrics

We track the performance of docs.basted.ru to ensure an optimal user experience. Based on the recent Lighthouse audit, the site demonstrates high performance across multiple metrics. Below are the key findings and optimization practices:

### Lighthouse Scores

The site was evaluated using Lighthouse on both desktop and mobile. Here are the results:

| Category         | Desktop Score | Mobile Score | Opportunity              |
|------------------|---------------|--------------|--------------------------|
| Performance      | 99            | 72           | Mobile performance can be improved by reducing unused CSS and deferring non-critical JavaScript |
| Accessibility    | 82            | 82           | -                        |
| Best Practices   | 100           | 100          | -                        |
| SEO              | 100           | 100          | -                        |

#### Real User Metrics:

| Category                       | Desktop Score | Mobile Score |
|--------------------------------|---------------|--------------|
| FID (First Input Delay)        | 0.3 s         | 2.87 s       |
| LCP (Largest Contentful Paint) | 1.0 s         | 5.23 s       |
| CLS (Cumulative Layout Shift)  | 0.0027        | 0            |
| TBT (Total Blocking Time)      | 0 ms          | 13.3 ms      |
| Speed Index                    | 0.73 s        | 5.1 s        |

These metrics demonstrate that the site loads quickly, responds to user input efficiently, and maintains layout stability, providing an overall smooth experience for visitors.

## Contributing

We welcome contributions! If you find errors, have suggestions for improvement, or want to add new content, follow these steps:

1. Fork the Repository and clone it to your local machine.
2. Create a New Branch for your changes.
3. Make Changes: This can include:
   - Fixing typos or inaccuracies
   - Adding new sections or expanding on existing topics
   - Improving examples for clarity
4. Submit a Pull Request to the main repository.

Please ensure that your contributions maintain the clarity and quality of the content.

## License

This project is licensed under the [Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/). You are free to use, share, and adapt the content for non-commercial purposes, as long as you provide proper attribution and do not use the material for commercial purposes.

## Contact

For any questions or feedback:

- Email: [admin@basted.ru](mailto:admin@basted.ru)
- GitHub Issues: [Create an Issue](https://github.com/basted/docs.basted.ru/issues)
