# Fuzzy Logic-Based Drone Landing Controller

## Overview

Autonomous drones require precise and safe landing procedures, especially under variable environmental conditions. Traditional control systems may struggle with uncertain or imprecise data during descent. Fuzzy logic, inspired by human reasoning, offers a flexible way to deal with these uncertainties by converting expert knowledge into a set of intuitive rules.

This project aims to create a fuzzy logic controller that dynamically adjusts the drone’s descent and positioning behavior using multiple real-time inputs. The result is a smoother and safer landing approach that can adapt to various environmental factors.

## Project Goal

To develop a fuzzy logic controller that helps a drone land smoothly and safely by adjusting its descent behavior based on real-time input parameters.

## Why This Approach?

- **Handles Uncertainty Gracefully**: Fuzzy logic allows the system to make decisions based on vague inputs like “low altitude” or “slightly off center.”
- **No Need for Complex Physics-Based Models**: Relies on human-like reasoning instead of precise equations.
- **Easy Rule Integration**: Control behavior is defined using simple IF-THEN rules that can be tuned easily.

## Input Parameters

- **Altitude**: Distance to ground (range: 0 to 10 meters)
- **Vertical Speed**: Descent rate of the drone (range: 0 to 3 m/s)
- **Landing Pad Alignment**: How centered the drone is over the pad (range: 0 to 1)
- **Wind Stability**: Stability of wind conditions (range: 0 to 1)

## Output Parameters

- **Throttle Adjustment**: Fine-tunes the descent speed (range: -1 to 1)
- **Position Correction Intensity**: Controls how much lateral movement is applied to re-center the drone (range: 0 to 1)

## Methodology

1. **Fuzzy Set Creation**:
   - Membership functions for all inputs and outputs (e.g., ZMF, SMF, Trimf, Trapmf, Gaussian).
   - Linguistic variables like: `low`, `medium`, `high`, `slow`, `moderate`, `fast`, `aligned`, `misaligned`, etc.

2. **Rule Base**:
   - 54 fuzzy rules created to cover all combinations of input conditions.

3. **Inference System**:
   - Mamdani-style fuzzy inference is used.
   - Defuzzification is done using centroid method to compute crisp output values.

## Dataset

This is a control simulation project, not based on a dataset but on fuzzy rule design and input simulation. Multiple test cases were constructed to evaluate behavior.

## Experiments

### Experiment 1: Smooth and Safe Conditions

- **Altitude**: Low  
- **Vertical Speed**: Slow  
- **Landing Pad Alignment**: Well aligned  
- **Wind Stability**: Stable  

**Expected Output**:  
Throttle adjustment should gently decrease, and position correction should be minimal.

### Experiment 2: Challenging Scenario

- **Altitude**: High  
- **Vertical Speed**: Fast  
- **Landing Pad Alignment**: Misaligned  
- **Wind Stability**: Unstable  

**Expected Output**:  
Throttle should reduce drastically and position correction intensity should be high.

## Technologies Used

- Python
- scikit-fuzzy (`skfuzzy`)
- NumPy
- Matplotlib

## Results Summary

- Membership function graphs for all inputs and outputs
- Smooth interpolation between linguistic values
- Visual rule activations and outputs for each scenario
- Control surfaces showing interaction of input-output behavior

---

**Prepared by:** Nashat Alfarajat
