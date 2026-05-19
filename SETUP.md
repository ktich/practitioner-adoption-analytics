# Setup guide — ECD Practitioner Analytics

## Step 1: Create the GitHub repo

1. Go to github.com → New repository
2. Name it: ecd-practitioner-analytics
3. Set to Public (required for free GitHub Pages)
4. Do NOT initialise with README (we'll push ours)
5. Click Create repository

## Step 2: Set up locally

In your terminal:

  git init ecd-practitioner-analytics
  cd ecd-practitioner-analytics

Copy all files from this output folder into that directory:
  _quarto.yml
  index.qmd
  styles.css
  README.md
  .github/workflows/quarto-publish.yml

Create the data folder and add your CSVs:
  mkdir data
  # copy in: funnel-counts.csv, features.csv

## Step 3: Push to GitHub

  git add .
  git commit -m "Initial commit — ECD practitioner analytics"
  git branch -M main
  git remote add origin https://github.com/YOUR_USERNAME/ecd-practitioner-analytics.git
  git push -u origin main

## Step 4: Enable GitHub Pages

1. Go to your repo → Settings → Pages
2. Source: GitHub Actions
3. Save

The workflow in .github/workflows/quarto-publish.yml will run automatically
on every push to main. First build takes ~3-4 minutes.

Your site will be live at:
  https://YOUR_USERNAME.github.io/ecd-practitioner-analytics

## Step 5: Update README links

In README.md, replace:
  https://[your-username].github.io/ecd-practitioner-analytics
  
with your actual URL.

Also update the LinkedIn and GitHub links at the bottom of index.qmd.

## Data file format

data/funnel-counts.csv expects columns:
  Step, Count, % of registered

data/features.csv expects columns:
  feature, pct_of_all, pct_of_converted

## To render locally (optional)

Install Quarto: https://quarto.org/docs/get-started/
Then run:
  quarto preview    # live preview in browser
  quarto render     # renders to docs/ folder
