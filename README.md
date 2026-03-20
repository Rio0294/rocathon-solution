# rocathon-solution
Build a semantic projected score search engine for rocathon where users can search for creators by category and vibe. Then rank them by GMV and projected score. 

The submission returns 8 results instead of 10. A match_threshold of 0.3 was chosen to make sure only creators who are genuinely relevant to the query are returned. Higher values (e.g., 0.5) would return too few results from our 200-creator dataset. Lower values (e.g., 0.1) would allow unrelated creators. 0.3 is relevant enough to match the brand vibe, loose enough to return meaningful results.
Thus, balancing creative fit with commercial viability.
