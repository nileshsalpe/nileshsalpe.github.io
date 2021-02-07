## Table of Content

- [General](#general) 
    - [Right Mindset](#right-mindset)
    - [Dedicated time slot for review](#dedicated-time-slot-for-review)
    - [Avoid Silos](#avoid-silos)
    - [Avoid conflicts](#avoid-conflicts)
- [Before CR]()
    - [Self-Review](#self-review)
    - [Commit Size](#commit-size)
    - [Background Information](background-information)
    - [Choosing Reviewers](choosing-reviewers)
    - [Deadlines](#deadlines)
- [In CR](#in-cr)
    - [Don't be evil](##dont-be-evil)
    - [Understand constraints](#understand-constraints)
    - [Handling the Comments](#handling-the-comments)
    - [Conflict Resolution](#conflict-resolution)
[After CR](#after-cr)
    - [After CR approved](#after-cr-approved)
    - [If CR rejected](#if-cr-rejected)
    
    
## General

### Right Mindset
- Shared responsibility to improve the product
- Learn from each other
- Opportunity to understand new area in product
- Mentoring

### Dedicated time slot for review

Team gives dedicated time daily for code review.
Example morning 10.30 to 11 am all will do code review if they have assigned one. Book calendar of team to do so for timely and quality code reviews.

### Avoid Silos
Avoid code brother's environment so no two persons always review each other's code. No islands of coder and reviewers.​

### Avoid conflicts
by having team consensus on general topics like​
- Code style and formatting (prettier, check style)​
- Language Conventions (Java, Python, Golang, Nodejs)​
- Framework conventions (Spring, Hibernate, Rest APIs, Swagger etc.)​
- Third party approved list of libraries​
- Realistic code coverage thresholds line/branch/function converge. Example 90% for line, 90% for branch, 80% for function etc.

## Before CR

### Self-Review
- Self-Review, You have explained code to yourself first before adding any reviewer.

### Commit Size
- Code commit size should not be more than ~10 files. Code review should finish in ~ 30 min.
- Code review should not need half or one day to review CR. it should be in small manageable chunks.

### Background Information
- Assume code reviewer don't know anything about feature or design decision. ​- 
- You have relevant documentation in internal wiki/task tracking tools for the change,  add links details in task in project management tools like JIRA, Rally, Team Foundation Server etc.
- Always mentions how you have tested the code. Add links for details for testing data and results in project management tools like like JIRA.

### Choosing Reviewers
- Choose one from current team (required) and other from another team (optional) for code review.
- Reviewer can reject to review code if he has other commitments or lacks knowledge in area of code changes.

### Deadlines
- Mention realistic deadline for code review  - give at least one day. Mention that in daily standup if you have urgent need in exceptional cases like fixing prod issue etc. ​
- If reviewer is too much busy or not comfortable in area of code change, he should communicate in stand-ups. 

## In CR

### Don't be evil
- If reviewer don’t understand code, ask clear to the point questions.
- Comments should lead to solution not to conflicts. Provide sample code in comment for more context.
- Reviewer should not criticize developer but the code. Give clear, constructive comments. Keep comment to point and avoid passion adjective like dumb, crazy stupid, wonderful etc.
- Comments should not contain personal blames or complaint , sarcastic, personal (yours, mine theirs etc.) content like.
    
    `You must understand by doing this will decrease the performance.`
    
    `You should not have retuned this from method it so bullshit !!!`

instead comment like this

    use xyz to increase performance by 2x.
    
    return this from function in case of error

- Appreciate code if code has done something very elegant and learn from it.

### Understand constraints
- Reviewer should understand constraints of developer.
  - timeline
    - It could be production bug need to fix what is causing problem right now than ideal fix.
  - infra
     - May be current cloud dont have support for sticky session so we have to some hacks.
     - It many not support automatic scaling we have to do manually 
     - It many not support particualr technology say it supports SOLR as service but not elastic search due to company wide decision.
   - dependent systems/services/product 
      - Need to call two different APIs instead service efficiently returning desired results in single API call.
      - It does not support async mechanism for time taking reqeust so you have to poll for results.
      - It does not support pagination and there are chances of going out of memory by fetching all results in one call.
      - It may return wrong response codes in case of errors say it returns HTTP 500 for auth error due to bad design.
    - evolution path etc. and assumptions teams' best practices for coding etc.
      - The team is developing quick proto-type and want to get things working fast.

### Handling the Comments
- Developer should take a moment back and consider yourself in reviewers' shoes and explain code to themself first.
- Developer should address code either by adding more comments in code or changing code to be clearer/performant.
- Developer should address or acknowledge all the comments.
- Reviewer should add nit: (nitpick) for non-critical comments. Example renaming, extra brackets etc.

### Conflict Resolution
- Facts or data points override personal preferences of coding.​
- Team's styling guide for naming, spaces, file size, usage of library etc. overrides personal preferences of coding.
- If there are too many iterations say 4-5, reviewer and code need to sync either through meeting to resolve the conflicts.
- If that does not solve involve third person and take decision based on time and cost investments to returns of code changes.
- If that does not solve involve manager and escalate concern ​
- Developer can reject review comments by citing valid reason like time constraints or hidden assumptions etc.

## After CR

### After CR approved
- All checks in pipeline are passed – build/code coverage/static code analysis etc.
- Track changes got merge in destination branch - user squash and merge so that commit history is clean.
- Create tasks or stories if there are any follow up items.
- Track it reflects in latest artefacts in pre-prod environment.
- Sanity check after merge in pre-prod could help.

### If CR rejected
- Developer and reviewer decide next steps with managers involvement.
- This should happen either if developer is working in silos or CR size  is big like entire feature.

