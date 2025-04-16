Staging ground for maintainers to collaborate on torch release notes. Houses various artifacts that chronicle the release notes starting with 2.7.

The file structure is as follows:
- X.Y.Z/   (release version, e.g., 2.7.0)
  - done/  (contains all .mds containing completed release notes)
    - results_*.md
  - todo/  (contains all .mds containing in progress release notes, disjoint from done/)
    - results_*.md
  - commitlist.csv   (contains all new commits in the release, this file is generated by a script)
  - final.md   (the final coagulated release notes)
  - miscategorized.md   (contains commits that were miscategorized)
- .gitignore
- final_template.md   (a skeleton template for final.md)
- LICENSE
- README.md   (this file)

The scripts to generate relevant artifacts are in https://github.com/pytorch/pytorch/tree/main/scripts/release_notes.
