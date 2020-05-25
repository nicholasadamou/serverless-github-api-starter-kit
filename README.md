# Serverless GitHub API Starter Kit

This is a starter project for accessing the GitHub API using GraphQL through a serverless [WebTasks](https://webtask.io) instance.

## Setting up [WebTasks](https://webtask.io)

In order to make the asynchronous calls to the [Github API](https://developer.github.com/v4/), we must set up a serverless end-point that we can use to fetch information against GitHub's API (e.g. [`functions/index.js`](functions/index.js)).

To install the dependencies necessary to use WebTask's cli, run the following:

```bash
yarn wt:install
```

To create the function within WebTask, run the following:

```bash
yarn wt:create
```

⚠️ **Please Note**: If you don't run `yarn wt:create`, this module will not exist within the WebTasks Dashboard. You must run `yarn wt:create` prior to adding secrets to a given WebTask.

This function will install `axios` and the `wt-cli` which we need in order to make calls to GitHub's end-point.

However, we need to add our GitHub Personal Access Token to the `index` web-task. To do this, run the following:

```bash
yarn wt:edit
```

This will open the WebTasks Dashboard. Click on the `index` module in the explorer, then click on the wrench in the upper-left-hand-corner of the editor and select `secrets`. Click `Add Secret` and enter the following information being sure to type the _key_ value correctly:

```text
Key: GITHUB_API_TOKEN
Value: <Your-Github-Personal-Access-Token>
```

To learn more about adding secrets to a WebTask module, read [here](https://webtask.io/docs/editor/secrets).

To start the WebTask's development server execute the following:

```bash
yarn wt:serve
```

If you have made changes to [`functions/index.js`](functions/index.js), you must update the deployed WebTask function using:

```bash
yarn wt:update
```

To learn more about [WebTasks](https://webtask.io/) and how to use it, please visit the [WebTask Documentation](https://webtask.io/docs/101).

## License

'serverless-github-api' is © Nicholas Adamou.

It is free software, and may be redistributed under the terms specified in the [LICENSE] file.

[LICENSE]: LICENSE
