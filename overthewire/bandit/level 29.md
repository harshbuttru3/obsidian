There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
## Solution : 
The password for next level is "qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL"

Cloned the repo same as previous level, but this time there wasn't any password in `README` file nor in commit logs(it says no password in production). checked all branches via the command : `git branch -a`, switched to `dev` branch. `git checkout dev`, 
in `README.md` file of this branch we got the password.