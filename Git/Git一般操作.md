# Git一般操作

### undo `git add`
`git reset HEAD <filename>`

### undo working directory modification
`git checkout -- <filename>`

### 回退到之前的 commit
`git reset --hard <commit no.>`  
`git reset --hard HEAD^`  
`git reset --hard HEAD^^`  
`git reset --hard HEAD~100`

---

## References:
[On undoing, fixing, or removing commits in git](http://sethrobertson.github.io/GitFixUm/fixup.html)