# pulse: A Network Knowledge Base

### Install Github Command Line Interface
type -p curl >/dev/null || sudo apt install curl -y
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg \
&& sudo chmod go+r /usr/share/keyrings/githubcli-archive-keyring.gpg \
&& echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null \
&& sudo apt update \
&& sudo apt install gh -y

<<<<<<< Updated upstream
### Having SSH problems?
- gh auth login

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
=======
To see the content on the base check out the [[Pulse Knowledge Base]]


## Links

[[Dework]] -> 
Github repo


## [[How to contribute?]]

If you'd like to contribute to the knowledge base check out open tasks and issues to develop the content of a specific topic:
- [[Github]]: check open issues on github and open a pull request for your contribution
- [[Dework]]: use it to see open tasks or check them directly on github

Tasks and issues are opened only for specific topics to be developed. If you'd like to contribute in any other way please do so on the Github repo by opening pull requests and pushing changes to the main branch once complete.


## [[Infrastructure]]

Check out the linked pages to see how the integration works and its role in it and how to setup each piece:
1. [[Dework]] - tasks assignment
	- used by contributors to check and apply for tasks
2. [[Github]] - git-versioned storage and editing of repository
	- used by contributors to check and work on files and submit/push changes once it's complete
3. [[Github Desktop]] - sync mechanism between the repo and a local folder
	- used to integrate the repo as a vault on [[Obsidian]]
4. [[Obsidian]] - read/writing platform
	- used by contributors to access and edit (through [[Github Desktop]]) the knowledge base with support to links and the [[Graph view]]
5. [[Obsidian Publish]] - Obsidian publishing platform
	- used by anyone to check the open knowledge base with support to links and the [[Graph view]]


### Integrations

Check out how integrations are setup and work here:
- [[Dework <> Github]]
- [[Github <> Obsidian]]


## Processes

- [[Creating a new task]]
- [[Contribute to a task]]
- [[Do other contributions to the knowledge base]]



## Docs

Learn more about the knowledge base:
[[Integrations and info flow]]
[[Admin setup]]
[[Contribution flow]]
[[Issue template]]
[[Note template]]
[[Kanban]]
>>>>>>> Stashed changes
