🧑‍💻 Setup (Local repo in VS Code)
Open a folder in Visual Studio Code
Open terminal inside VS Code
Initialize Git:
git init

Create a file:

echo "Hello world" > file.txt
git add .
git commit -m "initial commit"
🌿 Branching Workflow (Local)
1. Create first branch (branch-a)
git checkout -b branch-a

Make a change:

echo "Change from A" > file.txt
git commit -am "update from branch A"
2. Create second branch (branch-b from main)

Go back to main:

git checkout main

Create another branch:

git checkout -b branch-b

Make a conflicting change:

echo "Change from B" > file.txt
git commit -am "update from branch B"
⚔️ Merge Conflict (Local)

Now merge:

git checkout branch-a
git merge branch-b

You’ll get a conflict.
