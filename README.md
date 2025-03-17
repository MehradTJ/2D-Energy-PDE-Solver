# 🌡️ Numerical Solution of the 2D Energy Equation 🚀

## 📌 Overview
This project aims to solve the **2D incompressible energy equation** for a given velocity field using various **numerical methods**. The study includes:

- ✅ Validation of **flux and source integrals** against analytical solutions.
- ✅ Implementation of **explicit (RK-2, RK-4) and implicit (ADI) methods**.
- ✅ Investigation of **stability, accuracy, and computational performance**.
- ✅ Estimation of **thermal development length** in a **rectangular channel**.

---

## 🖼️ Problem Description
The governing **2D energy equation** is given by:

$$
\frac{\partial T}{\partial t} + u \frac{\partial T}{\partial x} + v \frac{\partial T}{\partial y} = \frac{1}{Re \cdot Pr} \left( \frac{\partial^2 T}{\partial x^2} + \frac{\partial^2 T}{\partial y^2} \right) + S
$$

where:
- **T**: Temperature
- **u, v**: Velocity components in x and y directions
- **Re**: Reynolds number
- **Pr**: Prandtl number
- **S**: Source term

🔹 The velocity field is given by:

$$
u(x, y) = 6 \bar{u} y (1 - y)
$$

$$
v(x, y) = 0
$$


🔹 Domain: Rectangular channel (length = 5 units, height = 1 unit)

🔹 Boundary Conditions:

- Top wall: $T_{\text{up}} = 1$ (top wall)
- Bottom wall: $T_{\text{bottom}} = 0$ (bottom wall)

🔹 **Parameters**:
- **Re = 25**, **Pr = 0.7**, **Ec = 0.1**

The Exact Solution of Flux Integral Equation is given by:

$$
\oint \left( u \frac{\partial T}{\partial x} + v \frac{\partial T}{\partial y} - \frac{1}{Re \cdot Pr} \nabla^2 T \right) ds = 
u_0 T_0 \pi \cos (2\pi x) y \sin (\pi y) + v_0 T_0 \pi x \cos (\pi x) \cos (2\pi y) + \frac{2T_0 \pi^2 \cos (\pi x) \sin (\pi y)}{Re \cdot Pr}
$$

the Exact Solution of the the Source Term is given by:

$$
S = \frac{Ec}{Re} \left[ 2 \left( \frac{\partial u}{\partial x} \right)^2 + 2 \left( \frac{\partial v}{\partial y} \right)^2 + \left( \frac{\partial u}{\partial y} + \frac{\partial v}{\partial x} \right)^2 \right]
$$

---

## 📂 Project Structure
📁 **2D-Energy-PDE-Solver**  
├── 📜 `2D-Energy-PDE-Solver.ipynb` - Jupyter Notebook with implementation 🧑‍💻  
├── 📜 `requirements.txt` - Required Python libraries 📦  
├── 📜 `README.md` - Project documentation 📖  
└── 📜 `LICENSE` - License file ⚖️  

---

## 🛠️ Numerical Methods Implemented
### **1️⃣ Flux Integral Validation**
✅ Discretization using **second-order central differences**  
✅ Analytical solution for verification  
✅ Calculation of **L1, L2, and L∞ error norms**  
✅ Accuracy analysis using mesh refinement  

### **2️⃣ Source Term Validation**
✅ Central differencing for source term evaluation  
✅ Analytical source term solution derivation  
✅ Error norm computation and **accuracy assessment**  

### **3️⃣ Implicit Time-Stepping Method (ADI Approach) for the Developed Flow Problem**
✅ Implementation of the **Thomas Algorithm**  
✅ Discretization using **ADI factorization**  
✅ Stability & accuracy evaluation  
✅ Visualization of **temperature contours and profiles**  


![Contour Plot of Temperature Distribution for Developed Flow in the Domain Using Numerical Solution](<Num Temp-1.png>)

*Figure 1: Contour Plot of Temperature Distribution for Developed Flow in the Domain Using Numerical Solution*


![Contour Plot of Temperature Distribution for Developed Flow in the Domain Obtained by Exact Solution](<Exact Temp-1.png>)

*Figure 2: Contour Plot of Temperature Distribution for Developed Flow in the Domain Obtained by Exact Solution*

### **4️⃣ Simulation of Developing Flow in a Rectangular Channel**
✅ Application of **realistic boundary conditions**  
✅ Computation of **wall heat flux** for thermal entry length estimation  

### **5️⃣ Explicit Time-Stepping Methods**
✅ **RK-2 and RK-4 methods** for explicit time integration  
✅ Comparative analysis of **accuracy and runtime**  
✅ Heat flux analysis for **thermal development length estimation**

![Contour Plot of Temperature Distribution in Developing Flow Simulated with an Explicit Numerical Solution](<developing rk4-1.PNG>)

*Figure 3: Contour Plot of Temperature Distribution in Developing Flow Simulated with an Explicit Numerical Solution*

### **6️⃣ Computational Performance Analysis**
✅ Benchmarking of **CPU time** for implicit vs explicit methods  
✅ Performance comparison of **ADI, RK-2, and RK-4**  

---

## 📊 Results & Findings
| Method | Speed ⏳ | Accuracy 🎯 |
|--------|--------|-----------|
| Gauss-Seidel | Moderate | High |
| Jacobi | Slow | High |
| SOR (ω=1.5) | Fastest (Iterative) | High |
| Line SOR | Faster than Gauss-Seidel | High |
| Fully Implicit | **Fastest Overall** | **Very High** |

📌 **Key Observations:**
- **Explicit methods (RK-2, RK-4)** require **small time steps** for stability but are **computationally efficient**.
- **Implicit methods (ADI)** allow **larger time steps** but **require more computation**.
- **Thermal entry length** is estimated to be **30–35 meters**.

---

## 🚀 How to Run
1️⃣ Clone the repository:
```bash
  git clone https://github.com/MehradTJ/2D-Energy-PDE-Solver.git
  cd 2D-Energy-PDE-Solver
```
2️⃣ Install dependencies:
```bash
  pip install -r requirements.txt
```
3️⃣ Open the **Jupyter Notebook** and run the cells:
```bash
  jupyter notebook 2D-Energy-PDE-Solver.ipynb
```

---

## 🔮 Future Improvements  
🔹 Adaptive mesh refinement for better accuracy.  
🔹 Application to **complex geometries & boundary conditions**.  

---

## 📜 License
This project is licensed under the **MIT License**. See the `LICENSE` file for details. ✅

---

## 🙌 Contributions
Feel free to **fork** this repository, create **issues**, and submit **pull requests**! 🚀🎯
