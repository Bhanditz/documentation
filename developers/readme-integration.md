# README Integration

![](../.gitbook/assets/screen-shot-2019-01-24-at-6.28.10-pm.png)

To get help generating an integration like [this](https://github.com/mochajs/mocha#backers) or [this](https://github.com/babel/babel#open-collective-sponsors), follow these steps.

1. Install [Macdown](https://macdown.uranusjr.com/) to make it easy to compare PRs in the last step
2. Clone opencollective-cli

   ```text
   $ git clone https://github.com/opencollective/opencollective-cli
   ```

3. Checkout `setup` branch

   ```text
   $ git checkout setup
   ```

4. Build

   ```text
   $ npm run build`
   ```

5. Get a personal token from [GitHub's token page](https://github.com/settings/tokens). Check all the `repo` related permissions.
6. Create a file in your home directory \(on Mac OS X or Linux\) called `.opencollective.json` and add token in it:

   ```text
   { "github_token": "[YOUR_TOKEN]" }
   ```

7. Run cli for a given repo

   ```text
   $ ./dist/bin/opencollective.js setup -r [repo_owner/repo_name] -i
   ```

   Ex: To integrate with MochaJS \([https://github.com/mochajs/mocha](https://github.com/mochajs/mocha)\), run

   ```text
   ./dist/bin/opencollective.js setup -r mochajs/mocha -i
   ```

   `-i` makes it interactive.

8. Answer questions asked by the script - usually defaults are good to go with. Verify that the slug of project is same as the one in the database \(script guesses at it and is usually right\).
9. Script attempts to do several integrations across README.md, CONTRIBUTORS.md and ISSUE\_TEMPLATE.md. Most important ones are the two integrations on README.md: backers and sponsor badges at the top and adding backer/sponsor section near the bottom.

