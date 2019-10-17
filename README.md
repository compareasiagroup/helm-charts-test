# helm-charts TEST
For OpenSource projects - when we don't have time to push into helm/charts

charts are published to gh-pages branch:

Initial setup of gh-pages folder tracking remote branch:

```
mkdir gh-pages
cd gh-pages 
git init 
git remote add gh-pages git@github.com:compareasiagroup/helm-charts-test.git
git checkout --track gh-pages/gh-pages
```

Pushing a chart changes:
```
$ helm package private-charts-repo/ -d gh-pages/
Successfully packaged chart and saved it to: gh-pages/private-charts-repo-0.0.1.tgz

$ helm repo index gh-pages --url https://compareasiagroup.github.io/helm-charts-test/

$ cd gh-pages
$ git add . && git commit -am"Publishing private-charts-repo-0.0.1"
$ git push -u gh-pages gh-pages
```

Using these charts:
```
helm repo add cag-test https://compareasiagroup.github.io/helm-charts-test
"cag-test" has been added to your repositories
```