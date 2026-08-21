DAVY'S MAP EXPLORER v2.0 — LIVE SUPABASE IMPLEMENTATION
=======================================================

THIS IS THE FIRST LIVE-DATA RELEASE.

The page no longer reads Philadelphia political geography or Amanda's 2023
performance from bundled data.js snapshots. It calls the live Supabase project
THE PORTAL using read-only RPC functions and a browser-safe publishable key.

LIVE NOW
--------
- Geography selector options come from Supabase.
- Current precinct geometry comes from Supabase.
- Ward outlines are generated from live precinct geometry in Supabase.
- Selected-area boundaries are generated in Supabase.
- 2023 Amanda McIllmurray performance is queried live from precinct results + turnout.
- Default view remains City Council District 6.
- Existing Map Explorer styling and controls are preserved.

SUPABASE FUNCTIONS ADDED
------------------------
public.map_geography_options()
public.map_precinct_geojson(text,text)
public.map_ward_geojson(text,text)
public.map_selected_boundary_geojson(text,text)
public.map_amanda_23p(text,text)

These functions are READ-ONLY and grant EXECUTE to anon/authenticated.
They do not expose a service-role key.

NEXT IMPLEMENTATION STEP
------------------------
Replace the one Amanda-specific function with generic catalog + result RPCs:
Election -> Contest -> Candidate/Choice -> Metric.
That will let every imported election automatically appear in the explorer.

OPENING
-------
Open index.html in a modern browser with internet access. The page needs access
to Supabase, MapLibre font glyphs, and OpenStreetMap basemap tiles.
