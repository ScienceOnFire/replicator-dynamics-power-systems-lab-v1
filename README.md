# Evolutionary Grid Control Lab V1

Run `npm install` then `npm run dev`. Build with `npm run build`. Vercel: Vite preset, output `dist`.

1. Generate base reference, then Run simulation. Pause or reset as needed.
2. Save the completed experiment. Reset returns to Base while retaining comparisons and scheduled events.
3. Activate a controller at any time, or schedule a switch before running. Only one advanced mode is active at once; droop stays on. MPC replaces the secondary command while active.
4. Compare traces and metrics, export CSV. Reset before changing scenario parameters. Clear unwanted scheduled events after reset.

Model: aggregate 50 Hz swing equation on 100 MW base, first-order turbine/governor, secondary actuator limits, quadratic allocation costs. RD uses simplex shares, distributed RD and consensus use a ring communication graph with optional delayed fitness. MPC searches bounded constant commands over a three-second prediction horizon; LQR is a reduced-order approximation. Adaptive mode is inertia-dependent gain scheduling, not online identification. Resource classes repeat for more than three resources. No AC network, individual rotor dynamics, storage SOC or validated converter model. Metrics use 0.1 s samples and settling is retrospective within the recorded horizon. Cost is a relative quadratic index, not currency. Educational simulation only.
