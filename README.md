# parser-model-hub
Storing parser models in github LFS

# How to set-up Github Large File Storage, with this repo as an example; 

## 1. Setup LFS upgraded github personal account
The first step is to have a personal Github account that has sufficient LFS storage quota and bandwidth; it could purchased from here: [https://docs.github.com/en/billing/managing-billing-for-git-large-file-storage/upgrading-git-large-file-storage]


## 2. Install LFS on local machine 
I recommend using mac, rather than ccc to upload; 
Please follow installation instruction here: [https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage?platform=mac]
Note, in my tests, Homebrew and MacPorts installation did not work for some reason. It's safer to go in the link[git-lfs.github.com] and click Download. 
Your install is successful with this message:
``` > Git LFS initialized. ```

## 3. Set up a repo to upload models

Create an emptty github repo to upload models; 

Clone it to your local machine;

## 4. Set up file-name pattern tracking

Since our models are stored as zip files, track all zips; 
```
git lfs track "*.zip"
git add .gitattributes
git commit -m "track *.zip files using Git LFS"
```

After running this comman, all the zip files added to this repo will be automatically stored in LFS; 

## 5. Copy the zipped models to this repo, and commit the changes; 

Our current models are stored in ```/dccstor/ykt-parse/SHARED/MODELS/AMR/transition-amr-parser.v0.5.2/```

After all models are stored in dir models:
```
git add models/*

git commit -m "upload transition-amr-parser models"

git push 
```

If the LFS setup is incorrect, the push will fail since it exceeded the maximum upload limit. 

If the LFS setup is correct, by clicking into the file on Github you should see ```Stored with Git LFS```



