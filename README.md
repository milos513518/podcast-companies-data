# Podcast Companies data

Companies whose people talked on tech podcasts about **onboarding, enablement and AI upskilling**, with what
they built for their own teams, the people to reach, open roles and full episode transcripts.
Built 2026-11-05. Contains named people with LinkedIn profiles: keep this repository **private**.

## Files

| File | One row per | Key columns |
|---|---|---|
| `data/companies.csv` | company (1,078) | `company`, `website`, `linkedin_company`, `in_apollo`, `artifacts`, `episodes` |
| `data/people.csv` | person at a company | `company`, `name`, `title`, `linkedin`, `type` (`podcast speaker`, `podcast guest`, `staff`), `area`, `notes` |
| `data/artifacts.csv` | thing a company built for its own people | `company`, `what_they_built`, `serves` (onboarding / enablement / ai_upskilling), `summary`, `why`, `how_it_works`, `outcome`, `quote`, `person`, `show`, `episode` |
| `data/open_roles.csv` | open job | `company`, `title`, `url`, `area` (Enablement / Onboarding / Technical product manager), `posted`, `checked` |
| `data/job_boards.csv` | company | `job_board_status` (`ok` or `no_public_board`), `source`, `total_open_roles`, `matching_roles`, `checked` |
| `transcripts/index.csv` | company × episode | `company`, `show`, `episode`, `date`, `transcript_file` |
| `transcripts/<show>/<episode>.txt` | episode | full transcript text (most are machine-made, without speaker labels) |
| `site/index.html` | — | the interactive page; open it via a local web server (`python3 -m http.server` inside `site/`) |

Join everything on the `company` column.

## Notes

- **Staff** are people whose title is technical program manager, engineering program manager, enablement or
  onboarding (sales / GTM enablement excluded), from Apollo on 2026-11-05.
- **Open roles** list only enablement (including support enablement), onboarding and technical product manager
  roles from the company's public Greenhouse, Ashby, Lever or SmartRecruiters board. `no_public_board` means the
  company was searched and has no public feed.
- Quotes in `artifacts.csv` were matched word for word against the transcripts; speaker attribution is inferred,
  so check `attribution` before contacting anyone.
- A handful of LinkedIn links came from web search rather than Apollo; spot-check before outreach.

- **Panels:** panel and roundtable episodes are attached to every company a panelist worked for at the time (Changelog News is a news show and is not treated as a panel). Panelists' employers that the show notes didn't give were found by web search and kept only when confirmed.
