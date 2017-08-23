gipsy
=====

A **proof-of-concept** how to "sync" repositories from GitLab to GitHub. Created due to the longstanding discussion in [this issue](https://gitlab.com/gitlab-org/gitlab-ce/issues/18732).

Any feedback about the setup, security considerations, improvements or PRs is highly appreciated.

Setup
-----

Go to the your **GitHub** [Personal access tokens](https://github.com/settings/tokens) page and create a new token with `public_repo` permissions.

:warning_sign: Consider using a separate account with limited repository access.

Add the following environment variables to the **GitLab** repository you want to push to GitHub:

-	`GITHUB_USERNAME` (myuser)
-	`GITHUB_TOKEN` (1a2b3c4d4f)
-	`GITHUB_REPO` (myuser/the-repo)

:warning_sign: We strongly recommend to only use the variables on *protected branches*.

See [.gitlab-ci.yml](.gitlab-ci.yml) mirror task for an example, add this `mirror` stage your **GitLab** repository.

Usage
-----

Push a commit to eg. the `master` branch of your **GitLab** repository.
