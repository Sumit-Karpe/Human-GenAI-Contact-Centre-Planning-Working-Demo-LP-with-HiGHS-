Human + GenAI Contact‑Centre Planning (LP with HiGHS)
What this script does:
1) Creates a synthetic multi-channel, multi-segment, multi-period dataset
2) Builds a linear program:
   - vars: in-house minutes (x), outsourced minutes (y),
           AI deflection shares (d), human-handled contacts (u), SLA slack (s)
   - objective: staffing cost + AI cost + SLA shortfall penalty + CSAT penalty
   - constraints: demand balance, capacity linking, SLA floors, deflection caps
3) Solves with scipy.optimize.linprog (HiGHS)
4) Returns results as DataFrames and saves CSVs


Planning model + working demo for joint staffing and AI‑deflection in a contact centre.
It builds and solves a linear program to decide, per channel/period/segment:

how much work to handle in‑house vs outsourced

what share of contacts to deflect to AI

how many contacts must be handled by humans

how much SLA shortfall to tolerate (with penalty)

The demo generates a synthetic, multi‑channel dataset and solves with scipy.optimize.linprog (HiGHS). Results are returned as pandas DataFrames (and can be saved to CSV). Optional plots available if matplotlib is installed.

