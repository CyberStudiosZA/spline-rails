# 📘 **SplineRail User Manual** (Unity 6+)

> ⚠️ **Important Requirements:**
> 
> - Unity **version 6.0 or higher**
>     
> - The **Unity Splines Package** must be installed
>     
> - Make sure you’re using the **CyberStudios SplineRail tools**
>     

---

## 🧱 Setup Guide

### Step 1: Create the Scene Setup

1. Add a GameObject (e.g., **Quad**) into your scene.
    
2. Create **two empty GameObjects** and name them (for example):
    
    - `SplineHandler`
        
    - `SplineGenerator`
        

---

### Step 2: Add Components

#### 🔧 In `SplineHandler`:

- Add the component:  
    **`SplineRail: Instantiator & Animator`**  
    _(Script: `SplineInstantiatorAnimator.cs`)_
    

#### 🔧 In `SplineGenerator`:

- Add the component:  
    **`SplineRail: Mesh to Spline`**  
    _(Script: `MeshToSpline.cs`)_
    

---

## 🎯 Using the Mesh to Spline Generator

1. **Assign a Mesh Object**  
    In the `Object To Knot` field, drag your GameObject (e.g., the Quad) that contains a **MeshFilter**.
    
2. **Set Sample Count**
    
    - `Sample Count` determines how many **Bezier Knots** will be generated.
        
    - More samples = a rounder, smoother spline.
        
3. **Generate the Spline**
    
    - Click the **"Generate Spline"** button (either from the Inspector or the context menu).
        
    - A new GameObject named `GeneratedSpline` will be created at runtime.
        
    - This GameObject includes a **SplineContainer** with a spline generated from your mesh.
        
4. **Adjusting the Spline**
    
    - In the Scene view, click the **Spline Tool** (top-left corner) to fine-tune the generated knots.
        
    - More sample counts = more curve fidelity.
        
    - To close the loop, check the **"Closed"** option inside the SplineContainer component.
        

> 💡 **Note:**  
> Depending on your mesh's shape and orientation, the generated spline may require **significant manual adjustments**. The `MeshToSpline` system generates knots based on mesh bounds in a circular fashion and might not perfectly match complex geometry.

---

## 🚂 Using the Spline Instantiator & Animator

After you’ve generated a spline:

1. **Assign the Spline**
    
    - Drag the `GeneratedSpline`’s **SplineContainer** into the `Spline Container` field.
        
2. **Assign a Prefab to Instantiate**
    
    - Set a prefab in the `Instantiated GO Prefab` field.
        
    - This prefab will be duplicated and animated along the spline.
        
3. **Control Spacing and Instantiation**
    
    - Use `Instantiated GO Spacing` to control the gap between each prefab.
        
    - OR check `Use Manual Count` and enter a fixed `Manual Count` instead.
        
4. **Adjust Appearance**
    
    - `Scale Multiplier`: Scales each instance.
        
    - `Forward Axis` & `Up Axis`: Controls which direction your object faces while traveling along the spline.
        
5. **Animation Settings**
    
    - `Animation Speed`: Controls movement speed.
        
    - The system will **loop** objects along the spline endlessly using `SplineAnimate`.
        
6. **To Reset the Rail**
    
    - Use the **"Reset Rail"** context menu on the component to clear and rebuild instances.
        

---

## ⚙️ Editor Button Shortcuts

- `MeshToSpline` includes a custom editor (`MeshToSplineEditor`) with a built-in **"Generate Spline"** button directly in the Inspector.
    

---

## 🧩 Example Use Cases

- Moving platforms, carts, or NPCs on tracks.
    
- Procedural placement of lights, trees, fences, or wires.
    
- Cinematic animation paths or patrol routes.
    

---

## 🛠️ Tips & Best Practices

- Adjust sample count depending on mesh size and desired spline detail.
    
- For 3D prefabs moving along the spline, use local axes (`Forward Axis`, `Up Axis`) for correct alignment.
    
- If spline isn't smooth enough, increase the sample count or manually tweak the spline using the **Spline Tool**.
    
---
[cyberstudios.co.za] []
