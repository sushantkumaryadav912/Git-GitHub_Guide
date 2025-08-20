# commitandpush_guide

# for any new repository

echo "# commitandpush_guide" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:sushantkumaryadav912/commitandpush_guide.git
git push -u origin main


# for existing repo

git remote add origin git@github.com:sushantkumaryadav912/commitandpush_guide.git
git branch -M main
git push -u origin main
