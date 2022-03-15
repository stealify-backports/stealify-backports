# stealify-backports
This is the Main Repo of the Organisation and stores documentation about our pratices.

## Target Audience
- Stealify Backport Maintainers
- Upstream Maintainers
- Package and Git Maintainance Engineers that want to learn about Designing and Scaling big Git Projects cross Organisation and Maintainer Interactions.

The Main goal of the Stealify backports org is to maintain portability of stealify patches as stealify includes and depends on a lot of open source that is not directly maintained by us we created the following strategie. 

## Subrepos + forks 
We use so called gitsub repos in our stealify projects to keep the commit noise of external dependencies low but we are able to backport patches back to upstream via this forks in this Organisation. 

they are here to collect and organize backporting efforts as also allow us to create many forked subbranches that we can join later. while we use in our core projects only our collections of subrepos where we develop and evaluate changes before we port them back to upstream if they are generic enough and usefull for the community.

## Usage
We will work on a stealify-cli client for that. As we guess this process will become more and more popular in the Stealify Lang Community and ECMAScript Community which already adopted so called monorepos. If any Term here in this docs sounds unfamilar simply google it copy paste it and read about it everything mentioned here is importent for stealify-backport maintainers. NOT For general Contributors of Stealify Projects when you come to this repo because you saw the url some how some where simply ignore it.

```
git clone stealify/<repo-name>
cd <repo-name>
gh repo fork rollup/rollup --clone=false --org stealify-backports # --fork-name rollup
git subrepo clone stealify-backports/<fork-name> <project/dir>
## Read the git subrepo docs if your a backporter 
## normal contributors will not know anything about this subrepo stuff 
## they use normal commits and pushes to the stealify/* repos and repo/directorys.

git subrepo push 
git fetch merge upstream to backports and then merge into the subrepos 
repeat 
```
