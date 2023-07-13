
# Trivy-Plugin-Aqua --- v0.141.0
 
## 2023-07-09
 
Added result enrichment using git fetch to get commit data per result.
 
### Added
- Result Commit Enrichment
  Use git fetch to add commit metadata for results.

### Fixed
 - Git command wrap 
   Wrapped internal git commands with `GIT_TERMINAL_PROMPT=0` - prevent hang on interactive authentication
 
## Additional requirements
  
  Result enrichment from git commits can be configured using the `TRIVY_FETCH_DEPTH` environment variable
    -1 = disables the feature and will not enrich results
    0 = will get all prev commits
    default = 100 - we fetch 100 past commits, can be configured to any integer larger than 0

## Known Issues
 Result enrichment using git fetch might slow down if a lot of commit data is fetched. 
- Use `TRIVY_FETCH_DEPTH` environment variable to configure commits fetched
 
## Support and Feedback
  https://support.aquasec.com/support/home
  
