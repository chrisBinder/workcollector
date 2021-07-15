# workcollector
Git hook that collects task numbers from commit messages to a text file  
Current format:  
`2021-07-16 : commit message`

# How-to
1. Enable git templates  
   `git config --global init.templatedir '~/.git-templates'`

    _This tells git to copy everything in ~/.git-templates to your per-project .git/ directory when you run git init_

2. Create a directory to hold the global hooks: `mkdir -p ~/.git-templates/hooks`  
  
3. Paste the `post-commit` into your hooks in `~/.git-templates/hooks`.  

4. Call `git init` in every repository that you want to equip with your post-commit hook 
  

# Useful alias:

```shell
function getwork() {
    if [ $# -eq 0 ]; then
        searchDate=$(date +"%Y-%m-%d")
    else
        searchDate=$(date +"%Y-$1-$2")
    fi
    echo "$(grep ${searchDate} PATHTOFILE)"
}
```

