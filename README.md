This repository collects, parses and renders available data for the app on obgyn violence.

# Organization

Repository data-vog

```
#goto repo root
cd ~/Documents/perso/GitHubPerso/data-obgyn-violence

#update latest posts from @stopvogfr
bash run_instaloader.sh

#run tesseract on first image of the post
bash run_tesseract.sh

#if not created before, create db
# poetry run python3 main/create_db.py

# update/populate the database
poetry run python3 main/update_db.py

# export in other github repo, commit and push results
poetry run python3 main/export_db.py

# commit in this repository instead, open a project on obgyn violence reports
cd ../misc/
git add export-obgyn/*
git commit -m 'update data'
git push
```

Once it is done, we still need to update the center list and match it to each post. 

From there, a csv export of the database can be done with
```
poetry run python3 main/export_db.py
```



# Repository app-vog

* R Shiny app
* calls database data-vog, publicly available on my GitHub account
