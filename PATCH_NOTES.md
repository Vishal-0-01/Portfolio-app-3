# Patch notes
1. optimizer.py run_walk_forward_backtest: drops funds with fewer than 60 observations in each training window, maps weights back to the full fund list, skips a year (recorded in "skipped_years") instead of crashing. Adds n_funds_used and funds_used per year.
2. optimizer.py _min_vol_weights: fallback random start is now seeded (reproducible).
3. optimizer.py compute_diagnostics + app.py /api/diagnostics: equal-weight return, volatility and HHI, fund Sortino ratios, correlation matrix, average pairwise correlation.
4. app.py: state["snapshot"] (data start, end, rows, funds, build time) exposed in /health.
5. frontend/index.html: 14th chart colour.
Before redeploying delete state_cache.pkl so the new fields are built.
