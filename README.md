What this script does:
1) Creates a synthetic multi-channel, multi-segment, multi-period dataset
2) Builds a linear program:
   - vars: in-house minutes (x), outsourced minutes (y),
           AI deflection shares (d), human-handled contacts (u), SLA slack (s)
   - objective: staffing cost + AI cost + SLA shortfall penalty + CSAT penalty
   - constraints: demand balance, capacity linking, SLA floors, deflection caps
3) Solves with scipy.optimize.linprog (HiGHS)
4) Returns results as DataFrames and saves CSVs
