This site is built with [Hugo](http://gohugo.io/).

Notes to self:

* Don't delete the `public/` directory. That's a submodule corresponding to berquist.github.io that `deploy.sh` uses. You will mess up your commit history if you delete it.
* If you have stray HTML files in `content/blog/`, you'll have weird entries under Blog, but they won't get published to the actual site.
