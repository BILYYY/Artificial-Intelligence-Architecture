# Dist‑o‑Meter — no‑electronics distance tool

A tiny web app (single HTML file) plus a DIY viewer made from a Monster bottle/can. It estimates distance to a target using **two** methods and also averages them for stability:

1) **Grid / similar triangles** using a 1 cm × 1 cm paper grid at the far end of the tube.  
2) **Two‑angle triangulation** using a small sideways move (baseline) and two angle readings.

---

## Files
- `index.html` – the web app (works offline).  
- `README.md` – this document.

## Build the device (Monster‑can viewer)
1. **Make the tube:** Cut the bottom off the bottle/can to make a tube.  
2. **Add the grid:** Tape a 1×1 cm paper grid over the wide/open end (the end **away** from your eye).  
3. **Eye (“lens”) position:** Put your eye at the **drinking end** (like you would sip). That’s the lens/eye point.  
4. **Angle helper:** Tape a small paper protractor near the eye end and add a straw or skewer as a sight pipe. Mark left/right so you can read angles.  
5. **Measure L:** Measure the inside length of the tube (eye to grid) = **L** in cm.

## How to measure

### Method A — Grid / similar triangles
- Pick one dimension of the target you know in real life (height **or** width).  
- Look through the eye end and count how many grid **squares** the target spans **along that same dimension**.  
- Put into the app:  
  - Real size (cm)  
  - Squares count (how many 1 cm squares)  
  - Square size (usually 1 cm)  
  - L (tube length, cm)  
- The app uses:  
  
**D_grid = (RealSize × L) / (Squares × SquareSize)**


### Method B — Two‑angle triangulation
- Stand at position A facing forward. Aim at the target and read the **front angle** θ₁ = angle from your straight‑ahead line to the target.  
- Slide **sideways** by a measured baseline **b** (e.g., 20 cm) to position B. Keep facing forward. Aim again and read the **side angle** θ₂ (again from straight‑ahead).  
- Put into the app: baseline b (cm), θ₁ (deg), θ₂ (deg).  
- The app uses:  
  
**D_tri = b / (tan θ₁ + tan θ₂)**


### Combined result
The app also shows **(D_grid + D_tri) ÷ 2**.

## Tips for accuracy
- Keep the grid perpendicular to the tube; don’t let it tilt.  
- Use the same eye spot each time (mark a notch).  
- Prefer small angles (&lt;~15°) for better tan() readings.  
- Choose a bigger real‑world feature if possible; count more squares.  
- Repeat 3–5 runs and average.

## Host on GitHub Pages
1. Create a public repo, e.g., `dist-o-meter`.  
2. Add `index.html` (and this `README.md`) to the root and commit.  
3. In **Settings → Pages**: Source = **Deploy from a branch**; Branch = `main` and folder `/ (root)`.  
4. Your site will appear at `https://<your-username>.github.io/dist-o-meter/`.

## License
MIT — reuse freely for school projects.
