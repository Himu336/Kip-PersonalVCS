# Kip - A Personal Version Control System

Kip is a simple, lightweight Version Control System (VCS) built with Node.js. Inspired by Git, it's designed as a learning project to understand the core concepts behind how version control systems work. Kip allows you to initialize a repository, track file changes, commit snapshots, and view your project's history right from the command line.

## Features

Kip provides the essential functionalities needed for basic version control:

- **Initialize Repository** (`init`): Creates a new `.kip` directory to store all the version history and necessary metadata.
- **Stage Files** (`add`): Adds file contents to the staging area (the index), preparing them for the next commit.
- **Commit Changes** (`commit`): Records a snapshot of the staged files to the commit history with a descriptive message. Each commit is linked to its parent, forming a chain of history.
- **View History** (`log`): Displays a log of all commits made, showing each commit's unique hash, timestamp, and message.
- **Inspect Commits** (`show`): Shows the changes introduced in a specific commit, including a colored diff for modified files.

## Usage

### Workflow

Here's a typical workflow for using Kip to manage a project.

#### 1. Initialize a Kip Repository

First, create a new Kip repository in your project's root directory. This only needs to be done once per project.

```bash
node kip.mjs init
```

This command creates a hidden `.kip` folder where all your version data will be stored.

#### 2. Add a File to the Staging Area

Create a new file and then use the `add` command to stage it.

```bash
# Create and add content to a file
echo "Hello, Kip!" > file1.txt

# Stage the file
node kip.mjs add file1.txt
```

#### 3. Commit the Staged File

Once your file is staged, you can commit it to the project history with a message.

```bash
node kip.mjs commit "Initial commit with file1.txt"
```

You will get a confirmation with the unique hash of your new commit.

#### 4. Make Changes and Commit Again

Now, let's modify the file and add a new one to see how Kip tracks changes.

```bash
# Modify the existing file
echo "Adding a new line." >> file1.txt

# Create a second file
echo "This is the second file." > file2.txt

# Stage both files
node kip.mjs add file1.txt
node kip.mjs add file2.txt

# Commit the new changes
node kip.mjs commit "Updated file1 and added file2"
```

#### 5. View the Project History

You can see the complete history of your project using the `log` command. It will display all the commits you've made in reverse chronological order.

```bash
node kip.mjs log
```
![Testing png 1](https://github.com/Himu336/Kip-PersonalVCS/blob/main/kip_testing1.png)

#### 6. Inspect a Specific Commit

To see the exact changes made in a particular commit, use the `show` command followed by the commit hash obtained from the `log`.

```bash
node kip.mjs show <your-commit-hash-here>
```
![Testing png 2](https://github.com/Himu336/Kip-PersonalVCS/blob/main/kip_testing2.png)
Kip will display a colored diff, showing which lines were added (`++`) and which were removed (`--`).

## Commands Reference

| Command | Description |
|---------|-------------|
| `node kip.mjs init` | Initialize a new Kip repository |
| `node kip.mjs add <file>` | Add a file to the staging area |
| `node kip.mjs commit "<message>"` | Commit staged changes with a message |
| `node kip.mjs log` | View commit history |
| `node kip.mjs show <hash>` | Show changes in a specific commit |

## Project Structure

```
your-project/
├── .kip/                 # Kip repository data
│   ├── objects/          # Stored file contents and commits
│   ├── index             # Staging area
│   └── HEAD              # Current commit reference
└── your-files...         # Your project files
```

## Learning Goals

This project demonstrates several key concepts in version control systems:

- **Object Storage**: How files and commits are stored and referenced
- **Staging Area**: The intermediate step between working directory and commits
- **Commit History**: How changes are linked together over time
- **Hashing**: Using SHA-1 hashes to uniquely identify content
- **Diffing**: Comparing file versions to show changes

## Contributing

This is a learning project, but contributions are welcome! Feel free to:

- Report bugs or issues
- Suggest new features
- Improve documentation
- Submit pull requests

## Acknowledgments

Inspired by Git and built as an educational tool to understand version control systems from the ground up.
