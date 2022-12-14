# Your most changed file

A little fun for cloudy summer days. The theory is to find files in your project that have the most changes. Could this class or file be refactored to be more sustainable?

```git
git log --pretty=format: --name-only | grep .php$ | sort | uniq -c | sort -rg | head -20
```

Source: https://janostlund.com/2021-06-30/find-most-changed-files
