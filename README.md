# Analyzing peer-review and publication speeds of MDPI journals



# 💾 Project Files Description

This project contains 3 executable files, one csv file,...

- code/01_get_paper_metadata.R - this R script downloads the metadata for 900k+ MDPI papers using the public OAI API. Executing this script takes a while. The result is saved in data/all_papers.csv
- code/02_preprocess_data.py - this Python script preprocesses all_papers.csv for subsequent web scraping. The result is saved in data/identifiers.csv.
- code/03_scrape.py - this Python script uses multithreading/parallel processing to scrape the publication histories of all papers contained in `data/identifiers.csv` and append the publication histories to `data/all_papers.csv`. The result is contained in `data/papers_complete.csv`.

# 📋 Execution Instruction

Note: I highly encourage you to work with `data/papers_complete.csv`. Getting the metadata and scraping the MDPI websites takes forever, even when using parallel processing. The scraping alone took more than a day on my M1 MacBook Air, and this was already fifteen times faster than using serial computing. 

If you must reproduce `data/papers_complete.csv`, do the following:
- execute code/01_get_paper_metadata.R, save the result in data/all_papers.csv
- execute code/02_preprocess_data.py, save the result in data/identifiers.csv.
- execute code/03_scrape.py, save the result in `data/papers_complete.csv`
