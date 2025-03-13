
# NEB GPA Calculator

A simple web application to calculate Grade Point Average (GPA) for Nepal Education Board (NEB) examinations.

## Overview

This Svelte-based application helps students calculate their GPA for Class 11 and 12 in the Science and Management streams according to the Nepal Education Board grading system.

## Features

- Stream selection (Science or Management)
- Two input methods:
  - Direct GPA entry 
  - Marks entry (which converts to GPA automatically)
- Subject-specific GPA calculation
- Overall GPA calculation
- Visual feedback on grades
- Mobile-responsive design

## How It Works

The GPA calculation follows the NEB formula:

```
GPA = (GPA(Theory) × Credit Hour(Theory) + GPA(Practical) × Credit Hour(Practical)) / Total Credit Hour
```

Different subjects have different credit hour allocations. For example:
- Nepali: Theory (2.25), Practical (0.75)
- English: Theory (3), Practical (1)
- Science subjects: Theory (3.75), Practical (1.25)

## Grading Scale

| Grade | Percentage | GPA Scale | Description |
|-------|------------|-----------|-------------|
| A+    | 90-100     | 4.0       | Outstanding |
| A     | 80-89      | 3.6       | Excellent   |
| B+    | 70-79      | 3.2       | Very Good   |
| B     | 60-69      | 2.8       | Good        |
| C+    | 50-59      | 2.4       | Above Average |
| C     | 40-49      | 2.0       | Average     |
| D+    | 30-39      | 1.8       | Below Average |
| D     | 20-29      | 1.6       | Above Insufficient |
| E/F   | 0-19       | 0.8       | Insufficient |

## Technologies Used

- [Svelte](https://svelte.dev/) - Frontend framework
- CSS - Styling
- JavaScript - Logic implementation

## Usage

1. Select your stream (Science or Management)
2. Choose your input method (GPA or Marks)
3. Enter your grades for each subject
4. View your calculated GPA and individual subject grades

## Development

This project is built with Vite and Svelte. To run it locally:

```bash
# Clone the repository
git clone https://github.com/anujpaude1/neb_gpa_calculator.git

# Navigate to the project directory
cd neb_gpa_calculator

# Install dependencies
npm install

# Start the development server
npm run dev
```

## Credits

- Created by [Anuj Paude](https://github.com/anujpaude1)
- Powered by [Enotes Nepal](https://www.enotesnepal.com)

## License

This project is open source.