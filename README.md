Surrogate Model For Microfluidic Plasma Separator

Project Overview
This application serves as an interactive design and simulation platform for a microfluidic device dedicated to separating plasma from whole blood. 
It leverages a Deep Learning (DL) Surrogate Model for rapid optimization of geometric parameters and uses the Gemini API for AI-powered analysis of the results.
The core goal is to find the optimal balance between high Plasma Purity, high Plasma Recovery, and low Pressure Drop across the device.

Key Features
AI-Powered Optimization: Uses a simulated DL surrogate model (optimizationService.ts) to efficiently search the multi-dimensional design parameter space to maximize an objective function (fitness).
Interactive Simulation: Features a draggable 3D chip view (InteractiveSimulation.tsx) that visually models particle separation (RBCs and Plasma) based on the optimized or manually adjusted parameters.
Real-time Performance Analysis: Displays real-time predicted performance metrics (Purity, Recovery, Pressure Drop) and simulation controls like flow rate and hematocrit.
Validated Performance Charts: Generates performance charts (PerformanceCharts.tsx) showing how the optimized design performs across varying flow rates and hematocrit levels.
Gemini AI Analysis: Utilizes the Gemini API to provide natural language insights and interpretations of the final optimized design and its performance characteristics (GeminiAnalysis.tsx).
Frontend Technologies: Built with React and TypeScript for a robust and type-safe user interface, using recharts for plotting.

Design Parameter Space
The optimization process explores the following bounds to find the best design:
Parameter             Min                  Max               Unit
Channel Width         50                   200                µm
Pillar Diameter       10                   50                 µm
Pillar Spacing        20                   100                µm
Number of Pillar      3                    15                 --
Inlet Flow Rate       0.5                  5.0                mL/hr
Blood Hematocrit      0.35                 0.45               --

This project is a web application built with Node.js and Vite.

Prerequisites
Node.js (required to run npm commands)
A Gemini API Key (for AI analysis functionality)

Installation and Setup
Clone the repository:
git clone https://github.com/YOUR_USERNAME/microfluidic-designer.git
cd microfluidic-plasma-separator-ai-designer

Install project dependencies:
npm install

Set up the API Key: Create a file named .env.local in the project root and add your Gemini API key:
GEMINI_API_KEY="YOUR_API_KEY_HERE"

Run the application:
npm run dev

The application will start, typically at http://localhost:5173. You can now navigate to the Design Optimizer panel to run the simulation.

File                                              Description
README.md                                         The main project documentation file.
package.json                                      "Defines project name, scripts, and dependencies (React, recharts, @google/genai)."
optimizationService.ts                            Contains the mockSurrogateModel and core logic for the optimization algorithm and condition testing.
OptimizerControl.tsx                              The UI component for initiating optimization and displaying parameter bounds.
InteractiveSimulation.tsx                         Handles the 3D visualization and real-time particle-level flow simulation.
ResultsDisplay.tsx                                Displays the final best design parameters and performance metrics (Predicted & Validated).
PerformanceCharts.tsx                             Renders performance metrics over varying flow rates and hematocrit levels using recharts.
GeminiAnalysis.tsx                                Fetches and formats the AI-powered analysis from the Gemini API for the optimized design.

Contributions are welcome! If you find a bug or have a feature request, please open an issue or submit a pull request.

Code Style: Follow standard TypeScript/React conventions.
