# pulse: A Network Knowledge Base

### Install Github Command Line Interface
type -p curl >/dev/null || sudo apt install curl -y
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y

### Having SSH problems?
- gh auth login
- cd directory you want to clone into
- git clone git@github.com:AgencyGives/pulse.git
- cd pulse
- git init

### Download Obsidian
https://obsidian.md/download

### Create a Vault for the Network Knowledge Base

### Clone the Network Knowledge Base into an Obsidian Vault
navigate to obsidian command: git clone git@github.com:AgencyGives/pulse.git

### Navigate through Branches in Obsidian

### Push changes to a branch in Obsidian

### Create a branch for a Dework task in Obsidian
go to command line in obsidian git checkout input this:
your-github-username/dw-55/dework-task

Dework Automation: After linking a task to a branch, if a Pull Request is opened, the task’s status will automatically change to In Review. Then, if the Pull Request is merged, the task will move to Done.
