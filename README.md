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

With only the required parameters:

```yaml
steps:
    - uses: actions/checkout@v3
      with:
        repository: metis-ai/hubtype-frontend-v2
        token: ${{ secrets.G_ACCESS_TOKEN }}

    - name: Run acceptance tests
      uses: metis-ai/acceptance-tests-action@main
      with:
        ENVIRONMENT_NAME: staging
        NETLIFY_AUTH_TOKEN: ${{ secrets.NETLIFY_AUTH_TOKEN }}
        NETLIFY_SITE_ID: Netlify's site id
        AWS_GH_ACTIONS_ACCESS_KEY_ID: ${{ secrets.AWS_GH_ACTIONS_ACCESS_KEY_ID }}
        AWS_GH_ACTIONS_SECRET_ACCESS_KEY: ${{ secrets.AWS_GH_ACTIONS_SECRET_ACCESS_KEY }}
```

With all parameters:

```yaml
steps:
    - uses: actions/checkout@v3
      with:
        repository: metis-ai/hubtype-frontend-v2
        token: ${{ secrets.G_ACCESS_TOKEN }}

    - name: Run acceptance tests
      uses: metis-ai/acceptance-tests-action@main
      with:
        ENVIRONMENT_NAME: staging
        TESTS_COMMAND: npm test-login
        RELEASE_CODENAME: v20230623.0
        NETLIFY_AUTH_TOKEN: ${{ secrets.NETLIFY_AUTH_TOKEN }}
        NETLIFY_SITE_ID: Netlify's site id
        SLACK_WEBHOOK_QA: ${{ secrets.SLACK_WEBHOOK_TEAM_PLATFORM }}
        CUSTOM_IMAGE: https://cdn-icons-png.flaticon.com/512/1581/1581884.png
        TESTS_SRC_DIR: ./acceptance
        AWS_GH_ACTIONS_ACCESS_KEY_ID: ${{ secrets.AWS_GH_ACTIONS_ACCESS_KEY_ID }}
        AWS_GH_ACTIONS_SECRET_ACCESS_KEY: ${{ secrets.AWS_GH_ACTIONS_SECRET_ACCESS_KEY }}
```

# License

The scripts and documentation in this project are released under the [MIT License](LICENSE)
