I created the repo through github in the browser then:

```
git clone https://github.com/robertvi/metabolism_model.git
...
git remote set-url origin git@github.com:robertvi/metabolism_model.git
git push
```

Now able to push back to github.

Or even easier:

```
git clone git@github.com:robertvi/metabolism_model.git
...
git push
```

This sets up using ssh as the comms method from the beginning, and this works since I already have an ssh key setup through github.