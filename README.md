# ttb-label-verifier-ai
Prototype application that uses OCR and rule-based validation to verify alcohol beverage labels against TTB application data, supporting single and batch review workflows.
# AI-Powered Alcohol Label Verification App

## Overview
This project is a prototype AI system designed to support TTB compliance review by automatically verifying alcohol beverage labels against required regulatory fields.

The system uses OCR to extract text from label images and compares extracted data against expected compliance rules to classify labels as:
- PASS
- REVIEW
- FAIL

---

## Problem Statement
The TTB processes ~150,000 label applications annually with manual review workflows. This prototype demonstrates how AI can reduce repetitive verification work such as:
- Checking brand name consistency
- Validating alcohol content (ABV)
- Confirming net contents
- Ensuring mandatory government warning statements are present

---

## Features
- Upload alcohol label images (JPG, PNG, PDF)
- OCR text extraction from labels
- Automated compliance validation
- Batch upload support
- Results dashboard with:
  - Total processed
  - Passed
  - Review required
  - Failed
- Simple, clean UI for non-technical users
- Fast processing target (< 5 seconds per label)

---

## Tech Stack
- Frontend: React + TypeScript
- Backend: FastAPI (Python)
- OCR: EasyOCR / PaddleOCR
- Image Processing: Python libraries (Pillow, OpenCV)

---

## How It Works
1. User uploads label image(s)
2. Backend extracts text using OCR
3. Extracted text is normalized and structured
4. Validator checks required fields:
   - Brand Name
   - Class/Type
   - ABV
   - Net Contents
   - Government Warning
5. System returns classification:
   - PASS → fully compliant
   - REVIEW → unclear or partial OCR match
   - FAIL → missing required fields

---

## Installation & Setup

### Backend
```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
