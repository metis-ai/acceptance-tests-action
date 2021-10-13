# acceptance-tests-action
Runs acceptance tests &amp; publish results. <BR>
You will need a repo with Serenity/JS tests and a Netlify site. <BR>
Internally, this action uses the following actions (Big thanks!:
- [actions/setup-node](https://github.com/actions/setup-node)
- [actions/cache](https://github.com/actions/cache)
- [nwtgck/actions-netlify](https://github.com/nwtgck/actions-netlify)
- [andstor/file-reader-action](https://github.com/andstor/file-reader-action)
- [rtCamp/action-slack-notify](https://github.com/rtCamp/action-slack-notify)



# Usage

See [action.yml](action.yml)

```yaml


steps:
    uses: actions/checkout@v2 # checkout the code of your bot

    - name: Run acceptance tests
        uses: metis-ai/acceptance-tests-action@main
        
        with:
          ENVIRONMENT_NAME: staging
          TESTS_SRC_DIR: relative_tests_dir
          RELEASE_CODENAME: XXX
          GITHUB TOKEN: your_gh_token
          NETLIFY_AUTH_TOKEN: Netlify's PAT #see https://github.com/nwtgck/actions-netlify#optional-inputs
          NETLIFY_SITE_ID: Netlify's site id
          SLACK_WEBHOOK_QA: configured_slack_webhook
```

# License
The scripts and documentation in this project are released under the [MIT License](LICENSE)
