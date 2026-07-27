# BMI Calculator — Lightning Web Component

A simple, visually polished **BMI (Body Mass Index) Calculator** built as a Salesforce Lightning Web Component (LWC), designed for public-facing Experience Cloud (Digital Experience) sites and portfolio showcases.

**Live Demo:** [https://vikaskumar-portfolio-dev-ed.develop.my.site.com/BMICalculator/](https://vikaskumar-portfolio-dev-ed.develop.my.site.com/BMICalculator/)

---

## 📌 Project Overview

This component lets a user enter their **height (cm)** and **weight (kg)**, then calculates their BMI using the standard formula:

```
BMI = weight (kg) / (height (m) × height (m))
```

Based on the calculated value, the component classifies the result into one of four standard categories and displays it back to the user, along with an educational panel explaining what each BMI range means.

The UI is built with a dark-themed card layout, custom CSS variables for consistent theming, and SLDS (Salesforce Lightning Design System) utility classes for spacing and form structure — all rendered over a full-bleed background image for a modern, food/health-themed aesthetic.

---

## 🧩 Component Architecture

| Layer | File | Responsibility |
|---|---|---|
| Template | `bmiCalculator.html` | Renders the input form and the results view conditionally |
| Styles | `bmiCalculator.css` | Dark card theme, custom CSS variables, button/result styling |
| Controller | `bmiCalculator.js` | Handles input changes, form submission, BMI calculation, and reset logic |

### Key Behaviors

- **Two-state UI** using `if:true` / `if:false` template directives:
  - **Input state** — shows the Height/Weight form
  - **Result state** — shows the calculated BMI and category, with a "Re-Calculate" button
- **Reactive properties**: `height`, `weight`, `bmiValue`, and `result` drive which view is rendered
- **Form submission** is intercepted (`event.preventDefault()`) so the calculation happens client-side without a page reload
- **BMI classification logic**:

  | BMI Range | Category |
  |---|---|
  | Under 18.5 | Underweight |
  | 18.5 – 24.9 | Healthy |
  | 25.0 – 29.9 | Overweight |
  | 30 and above | Obese |

- **Reset flow**: The `recalculate()` method clears all reactive properties, returning the user to the input form.

---

## 🎨 Styling Highlights

- Custom CSS variables (`:host()` scope) define a consistent color palette:
  - `--dark-blue` (card background)
  - `--light-pink` (accent / buttons / highlights)
  - `--light-blue` (result value highlight)
  - `--light-white` (text)
- Background image pulled from a Salesforce Static Resource (`/sfsites/c/resource/BMICalculator`)
- Rounded card (`border-radius: 38px`) with a distinct info panel below the calculator for BMI education content

---

## 🚀 Deployment Notes

- Built for deployment on an **Experience Cloud (Community) site** via a Static Resource for the background image
- Uses **SLDS classes** (`slds-form-element`, `slds-button`, `slds-var-*` spacing utilities) so it fits naturally within Salesforce-hosted pages
- No Apex/server-side dependency — the component is entirely self-contained and client-side, making it lightweight and fast to load

---

## 🖥️ Final Output

**Input Screen**
- Dark card titled "BMI Calculator"
- Height (cm) and Weight (kg) input fields
- Pink "Calculate" button
- Educational "What your BMI means" panel below the form, listing all four BMI categories

**Live URL:**
👉 [https://vikaskumar-portfolio-dev-ed.develop.my.site.com/BMICalculator/](https://vikaskumar-portfolio-dev-ed.develop.my.site.com/BMICalculator/)

*(See attached screenshot for the rendered UI on the live site.)*

---

## 👤 Author

**Vikaskumar Pandey**
Salesforce Developer 
