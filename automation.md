# Automation FTW

In order to version our github-hosted repositories we include a file (`VERSION.txt`)
in each of them, where we store the version number of the application.
We could use git tags but we're too lame for that :)

Also, some of the repos don't really have this file...   ...because they dont need
it (for example, we use some repos just to store documents etc etc and they dont
need a version number).

Our version numbers look like `Nx.y.z` where `N` is a common prefix we use for
all our `VERSION.txt`.

We have now decided that `N` is useless and would like to remove it from all our
`VERSION.txt` files, but we dont want to manually send a pull request to each
repo changing `Nx.y.z` to `x.y.z`.

Can you write an automated task that can do that for us? To test it, you can try
running the task on a user's or organization's public repos (but don't annoy them,
better to use your own github profile :)).

You can use either Bash, Python or Node.
