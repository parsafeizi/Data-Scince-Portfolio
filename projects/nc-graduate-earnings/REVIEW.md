# Project Two review and validation

Prepared October 3, 2026. **No commit, push, or publication has been performed.**

## Files and changes

| File | Change |
| --- | --- |
| `project.md` (repository root) | Added a Project Two entry above the existing NBA project, preserving its content. |
| `index.md` (repository root) | Added a Project Two link and summary. |
| `projects/nc-graduate-earnings/project.md` | Created the complete project narrative with Jekyll front matter, the 11 requested sections, five existing figures and interpretations, three verified APA-style references, reproducibility links, and AI disclosure. |
| `projects/nc-graduate-earnings/nc_graduate_earnings_analysis.ipynb` | Organized explanatory Markdown, clarified evaluation scope, added data checks and portable paths, and refreshed outputs through a complete execution. |
| `projects/nc-graduate-earnings/requirements.txt` | Recorded the Python package versions used for validation. |
| `projects/nc-graduate-earnings/data/cross_validation_model_results.csv` | Exported the four computed five-fold model results. |
| `projects/nc-graduate-earnings/data/test_set_model_results.csv` | Exported the four computed initial test-set results. |
| `projects/nc-graduate-earnings/data/random_forest_feature_importance.csv` | Exported computed permutation importance for the three predictors. |
| `projects/nc-graduate-earnings/REVIEW.md` | Added this review record and rubric comparison. |

No model-results CSV files were present in the project folder at initial inspection; the three result files above are new exports from the existing analysis. The source workbook, cleaned CSV, and all five original image files remain byte-for-byte unchanged. The unrelated `Untitled/` directory was not edited.

The project directory was already untracked when work began. Git's tracked diff therefore lists only the two portfolio navigation edits; the Project Two files must also be reviewed and explicitly added when publication is approved. Do not add `Untitled/` as part of this project.

## Important analysis choices preserved

- The original filtering logic, row order, 80/20 stratified split, random seeds, predictors, estimators, and model parameters are unchanged.
- Cross-validation changed from `n_jobs=-1` to `n_jobs=1` to eliminate multiprocessing shutdown errors. The folds and scores are unchanged.
- All original working code cells were retained. There were no separate obsolete experimental code cells requiring deletion.
- The notebook now resolves paths from either the project directory or the repository root, checks the expected dataset properties, and exports the computed result tables.
- The report distinguishes initial test-set results from full-data cross-validation. It explicitly states that the former is not an untouched final audit after the latter.
- The AI disclosure is written in the requested first person. Review it with the code and outputs before approving publication.

## Validation results

- **Notebook execution: passed.** Python 3.13.5, a fresh Jupyter kernel, 18 code cells executed in order from beginning to end. Execution was performed in a temporary project copy to protect the original data and images. Jupyter required permission to open local kernel ports outside the sandbox.
- **Notebook format: passed.** Valid nbformat 4.5 structure, sequential execution counts 1–18, no saved error or stderr outputs. A one-time Matplotlib font-cache progress message was removed after execution; numerical outputs were retained.
- **Dataset: passed.** 1,537 observations, 29 fields, 16 institutions, 6 cohorts; no missing retained values or duplicate observation keys. The regenerated cleaned dataset equals the existing CSV.
- **Results: passed.** Every confirmed R² and rounded dollar metric reproduced. See the table below.
- **Visualizations: passed.** All five regenerated figures are pixel-identical to the originals. The originals remain in place.
- **Local paths: passed.** Checked 30 local image/link references across the home page, main projects page, and new project page, resolving generated `.html` routes to their Markdown source. No missing local targets. The notebook's local writeup link also resolves.
- **Markdown: passed.** The new page parses as five images and four tables, with descriptive image text and an interpretation after every figure. Jekyll front matter declares the existing `default` layout. Added site links use relative `.html` routes suitable for the repository's GitHub Pages subpath.
- **References: verified.** Census documentation, the Georgetown report (including its title page), and the published Chetty et al. article were checked for author, date, title, and URL. Census anchors were checked against its HTML. Georgetown and Oxford/DOI direct scripted requests return HTTP 403, while the web research tool retrieves their content; this is an automated-access limitation rather than evidence of nonexistent citations.
- **GitHub notebook URL: pending publication.** The requested URL currently returns HTTP 404 because Project Two is not on `main` yet. It points to the correct repository, branch, and file path and must be rechecked after the approved push.
- **Whitespace: passed.** `git diff --check` plus checks of new Project Two text files.
- **Site preview/build: limited.** The live portfolio was reachable and identifies Jekyll 3.10.0. A temporary HTML preview was generated from the new Markdown using the existing live theme stylesheet. The repository has no Gemfile, local build workflow, or installed Jekyll, so no full Jekyll build was run. Browser security policy blocked opening the local preview, so visual browser verification remains incomplete. No repository theme or build configuration was changed.

| Model | Mean R² | Mean MAE | Mean RMSE |
| --- | ---: | ---: | ---: |
| Linear regression — baseline | 0.579 | $6,075 | $8,701 |
| Linear regression — expanded | 0.774 | $4,426 | $6,379 |
| Random forest — baseline | 0.577 | $6,073 | $8,715 |
| Random forest — expanded | 0.850 | $3,553 | $5,198 |

## Comparison against the 12 required assignment specifications

| # | Specification | Status and evidence |
| --- | --- | --- |
| 1 | Published Portfolio Project | **Pending approval and publication.** The labeled page and home/projects navigation are prepared locally. Actual GitHub Pages deployment and live route verification remain. |
| 2 | Machine-Learning Problem and Dataset | **Complete locally.** Problem Definition and Data Description identify regression, target/units, source snapshot, aggregate unit, variables, sample size, missingness, and duplicates. |
| 3 | Context and Supporting Research | **Complete locally.** Background connects three verified credible sources to data methodology, college fields, and institutional outcomes; References provides APA-style citations. |
| 4 | Data Preparation | **Complete locally.** Documents filters, 666 excluded target values, text cleanup, one-hot encoding, no scaling/target transformation, and reasons for the choices. |
| 5 | Data Understanding and Feature Selection | **Complete locally.** Summaries, distribution and cohort plots, upper-tail observations, uneven category coverage, and predictor selection rationale. |
| 6 | Training and Testing Strategy | **Complete locally.** Describes the 80/20 split, five folds, fixed seeds, training-only encoding, explicit feature selection, and limits of shared institutions and reused evaluation data. |
| 7 | Baseline Performance | **Complete locally.** Both degree-field-only baselines are reported and compared with their expanded counterparts. |
| 8 | Model Development and Comparison | **Complete locally.** Linear regression and random forest each have baseline and expanded variants; model settings are stated and the working code is preserved. |
| 9 | Model Evaluation | **Complete locally.** R², MAE, and RMSE are explained, confirmed results reproduced, and expanded random forest selected on all three metrics. |
| 10 | Model Interpretation | **Complete locally.** Permutation importance and actual-versus-predicted plots are interpreted with numerical values and noncausal caveats. |
| 11 | Ethics and Limitations | **Complete locally.** Coverage, suppression/missingness, aggregate inference, omitted variables, validation optimism, privacy, harms, and appropriate exploratory use are addressed. |
| 12 | Code and AI Transparency | **Content complete; public code access pending publication.** Direct GitHub notebook link, reproducibility files, citations, and requested AI disclosure are present. The notebook URL will become publicly accessible after the approved push. |

## Remaining review and publication steps

1. Review the project narrative, executed notebook, and first-person AI disclosure.
2. Approve a commit and push explicitly; none has been made.
3. After publication, verify the GitHub Pages build, project route, navigation, images, downloadable data, and GitHub notebook rendering. This is necessary to finish specification 1 and the public-access portion of specification 12.

The temporary preview is a convenience for local review, not evidence that a Jekyll deployment has passed.
