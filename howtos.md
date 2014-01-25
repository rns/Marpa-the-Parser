* how to remove unwanted commits from a pull request

    - you try to file a pull request and see that your branch <topic> contains unwanted commits to branch <master>
    
    - select commit on which you need to base your pull request -- <pr_base_commit>
        
        git checkout master
        git log --oneline
        
    - select all commits you need in the pull request

        git log --oneline
    
    - create new branch <topic1> from the <pr_base_commit>
        
      git branch <topic1> <pr_base_commit>
        
    - git checkout <topic1>
    
    - more the needed commits one by one, chronologically
    
        git cherry-pick <least recent commit>
        ...
        git cherry-pick <most recent commit>
    
    - git push --force origin topic1
