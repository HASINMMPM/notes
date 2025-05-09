Prepare and generate the v1.0.0 release build following our Git Flow process using \*_SourceTree._

### Steps to Complete

1. _Start the Release in SourceTree_
    - Click Git Flow > Start New Release
    - Name the release 1.0.0
    - This creates release/1.0.0 from develop
2. _Bump the Version_
    - Update the version number in relevant files (e.g., package.json, VERSION, etc.)
    - Commit the changes with message:  
       Bump version to 1.0.0
3. _Finish the Release_
    - Click Git Flow > Finish Release
    - Select release 1.0.0
    - Ensure the release is:
        - Merged into main
        - Tagged as v1.0.0
        - Merged back into develop
4. _Push Changes_
    - Push main, develop, and all tags to origin
5. _Create a GitHub/GitLab Release_
    - Go to the repo → Releases → "Draft a new release"
    - Tag: v1.0.0
    - Add notes and publish

\*Acceptance Criteria:

- Release v1.0.0 is visible in Git with proper tag
- main and develop are both updated and pushed
- Version files reflect 1.0.0
- GitHub/GitLab release is published
