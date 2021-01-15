# evazangerle.at

This page uses Hugo and the academic template and is deployed on Github pages.

## Setup
```
# install hugo 
dnf install snapd
snap install hugo --channel=extended

# local setup
# fork https://github.com/sourcethemes/academic-kickstart
git clone https://github.com/evazangerle/academic-kickstart.git 
git submodule update --init --recursive

# start hugo, go to http://localhost:1313
hugo server
```


## Deployment

### Setup
Two repos are used: one for the code (fork of academic kickstart described above) and evazangerle.github.io, where resulting static pages are deployed. All this is taken from the [official Hugo documentation](cf.  https://sourcethemes.com/academic/docs/deployment/
).

```
# create evazangerle.github.io
# add evazangerle.github.io as submodule in public folder (Hugo output folder)
git submodule add -f -b master https://github.com/evazangerle/evazangerle.github.io.git public
# in config/_default/config.toml, change baseurl to evazangerle.github.io
```


### Deploying
```
# run hugo to recreate pages, push to repo
hugo
cd public
git add *
git commit -m "message"
git push
```

## Updating
Config-file can be found in `config/_default/config.toml`, all content-files are located in `content`. 

When performing changes locally, these can be deployed locally:
```
hugo server
# open localhost:1313
```

### Updating publications
Publications are managed via bibtex, which are preprocessed via a python script ([academic](https://github.com/sourcethemes/academic-admin)). This script parses the bibtex file and creates md-files ready to be used by the templating engine:

```
academic import --bibtex /home/eva/git/cv/bib/publications.bib
```

To add a pdf for e.g., the entry vldb10, add the pdf-file named just like the created folder (vldb-10 folder menas vldb-10.pdf as name) in the vldb-10 folder.



## Resources
* [Hugo](https://gohugo.io/)
* [Academic](https://sourcethemes.com/academic/)
* [Why you should create your academic website with Academic and Hugo](https://georgecushen.com/create-your-website-with-hugo/)
# evazangerleat
