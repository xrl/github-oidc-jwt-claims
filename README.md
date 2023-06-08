## GitHub OIDC JWT Claims

Worried what tokens are available in your GitHub Actions token? Drop this action in your workflow and get the full nitty-gritty!

```

```

Background on JWTs in GHA:

 * [What are JWT tokens?](jwt.io)
 * [How do I fetch JWTs inside of a workflow?](https://github.com/actions/toolkit/tree/main/packages/core#oidc-token)

Because GHA JWTs are signed by GitHub, you can be pretty sure any properly signed token originated from the GitHub Actions system (unless they have been hacked and their signing key exfiltrated, of course, then all bets are off). But it's always good to do a deep match on the contents of the JWT so you can implement logic such as:

 * Any push event from repository XYZ can assume such-and-such AWS role
 * Any merge event on `main` can use such-and-such AWS role

Now you never have to generate service account passwords and store them as secrets. Generate short-lived credentials with AWS by exchanging JWTs with the WebIdentityAssume IAM API.
