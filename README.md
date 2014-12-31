# gitlab-ci-runner-python

This is docker image based on the Dockerfile provided by gitlabhq and codingforce.
- See https://github.com/gitlabhq/gitlab-ci-runner/blob/master/Dockerfile by Sytse Sijbrandij <sytse@gitlab.com> for the original.
- See https://github.com/bkw/gitlab-ci-runner-nodejs/master/Dockerfile by Bernhard Weisshuhn <bkw@codingforce.com> for the basis for this version.

Differences from the original:

- no mysql
- no postgres
- no redis
- switch to Ubuntu 14.04 from 12.04
- Ruby 2.0 from Ubuntu 14.04
- Python 2.6, 2.7, 3.3 and 3.4 (2.6 & 3.3 from Dead Snakes)
- pip and virtualenv installed

# Installation

This image is available as a [Trusted Build](https://index.docker.io/u/cardoe/gitlab-ci-runner-python/). Import the build like this:

	docker pull cardoe/gitlab-ci-runner-python

# Usage
Run like this:

	$ docker run \
		-d \
		-e CI_SERVER_URL=https://ci.example.com \
		-e REGISTRATION_TOKEN=replaceme \
		-e HOME=/root \
		-e GITLAB_SERVER_FQDN=gitlab.example.com \
		cardoe/gitlab-ci-runner-python

The new runner should show up in the GitLab CI interface on /runners
