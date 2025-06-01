# Student Score Calculator in 8086 Assembly Language

## 📘 Project Overview

This project is a **menu-driven application** developed in **8086 Assembly Language** that calculates and displays student academic performance metrics. It supports features like average score calculation, weighted averages, GPA mapping, letter grades, and percentage calculations. The program operates in a **DOS environment** using **INT 21h** for input/output operations.

---

## 🎯 Objective

To build a functional console-based calculator in 8086 assembly that:

- Accepts subject scores and weights from the user.
- Performs robust input validation.
- Computes and displays:
  - Average
  - Weighted Average
  - GPA (out of 4.0)
  - Letter Grade
  - Percentage

---

## 🧠 Features

- Menu-driven interface.
- Supports 2-digit (0–99) scores and 3-digit (0–999) marks.
- Handles non-digit and edge-case inputs gracefully.
- Uses **modular procedures** for input, calculation, and output.

---

## 🛠️ Program Architecture

### Data Segment

Defines:
- User prompts
- Result and error messages
- Variables: `score1`, `score2`, `score3`, `weight1`, `weight2`, `weight3`, `total_marks`, `max_marks`, `result`, `operation`

### Code Segment

Key labels and procedures:
- `main`: Initializes the program and handles looping through the menu.
- `display_menu`: Presents the main options.
- `read_number` / `read_three_digit_number`: Input readers with validation.
- `display_number`: Converts numeric results to ASCII for screen output.
- `calc_average`, `calc_weighted`, `calc_gpa`, `calc_letter_grade`, `calc_percentage`: Perform computations and store results.

---

## 📋 Menu Options

1. Calculate Average of 3 subject scores  
2. Calculate Weighted Average (user-defined weights)  
3. Compute GPA (4.0 scale)  
4. Determine Letter Grade (A–F)  
5. Calculate Percentage (total vs. max marks)  
6. Exit  

---

## 🔍 Example Results

| Input Type         | Example Input             | Output                      |
|--------------------|---------------------------|-----------------------------|
| Average            | `85, 90, 95`              | `Average Score = 90`        |
| Weighted Average   | `85,90,95` & `30,30,40`   | `Weighted Average ≈ 90`     |
| GPA                | Average = `85`            | `GPA = 3.0`                 |
| Letter Grade       | Average = `75`            | `Letter Grade = C (Average)`|
| Percentage         | `450 / 500`               | `Percentage = 90%`          |
| Invalid Input      | `ab`                      | `Error: Invalid Input!`     |

---

## ⚠️ Limitations

- **No decimal precision**: Results are truncated to integers.
- **Fixed ranges**: 2-digit scores, 3-digit marks.
- **Hard-coded grading scale**: GPA and letter grades.
- **No file I/O**: All input/output is terminal-based.
- **DOS-dependent**: Requires a DOS emulator like DOSBox to run.

---

## 🚀 How to Run

1. Install [DOSBox](https://www.dosbox.com/)
2. Assemble the `.asm` file using [TASM](https://archive.org/details/TASM_Complete)
3. Link the object file:
   ```bash
   tasm calculator.asm
   tlink calculator.obj
