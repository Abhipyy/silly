git --version
git config --global user.name "Ahijeet"
git config --global user.email "wfqawesfq@gmail.com"

git remote -v   \\check repo
git remote add origin https://github.com/YOUR_USERNAME/begin.git
git pull origin main --allow-unrelated-histories


touch file1.md
git status
git add .
git commit -m "update3files"
git push origin main

git checkout branch_name
git merge b2
git push origin main \\merging b2 into main