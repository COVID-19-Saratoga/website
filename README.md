# COVID-19-Saratoga

Website for volunteers to deliver groceries to Saratogan elderly and inform each other about conditions of nearby stores

# Git workflow

1. For a new bug fix or feature idea, add it to the [To do](https://github.com/COVID-19-Saratoga/COVID-19-Saratoga-Website/projects/3#column-8363440) column of the [project board](https://github.com/COVID-19-Saratoga/COVID-19-Saratoga-Website/projects/3).
2. When you can work on it, move it to [In progress](https://github.com/COVID-19-Saratoga/COVID-19-Saratoga-Website/projects/3), convert it to an issue, and self assign it.
3. Create a new branch with `git checkout -b [branch-name]` and `git push -u` (branches are `kebab-cased`).
4. Create a new pull request draft pointing to your branch. Make sure to comment `Fixes #[issue number]` for each issue it resolves (e.g., the one your converted when you moved the issue to `In progress`).
5. As you're working on your branch, to keep up to date with `master`, run `git rebase master` and `git push --force-with-lease`.
6. When you're done, click `Ready for review` and then `Squash and merge`.

## Deploy Your Own

Deploy your own Sapper project with ZEIT Now.

[![Deploy with ZEIT Now](https://zeit.co/button)](https://zeit.co/import/project?template=https://github.com/zeit/now/tree/master/examples/sapper)

_Live Example: https://sapper.now-examples.now.sh_

### How We Created This Example

To get started with Sapper deployed with ZEIT Now, you can use [degit](https://github.com/Rich-Harris/degit) to initialize the project:

```shell
$ npx degit "sveltejs/sapper-template#webpack" my-sapper-app
```

> The only change made is to change the build script in `package.json` to be `"sapper export"`.

### Deploying From Your Terminal

You can deploy your new Sapper project with a single command from your terminal using [Now CLI](https://zeit.co/download):

```shell
$ now
```
