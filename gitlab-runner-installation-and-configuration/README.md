# GitLab Runner Setup

## Download the runner
```bash
sudo curl -L --output /usr/local/bin/gitlab-runner https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64
```

## Give it permission to execute
```bash
sudo chmod +x /usr/local/bin/gitlab-runner
```

## Create a GitLab Runner user
```bash
sudo useradd --comment 'GitLab Runner' --create-home gitlab-runner --shell /bin/bash
```

## Install and run as a service
```bash
sudo gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner
sudo gitlab-runner start
```

## Register your GitLab Runner 
```bash
gitlab-runner register --url $GITLAB_URL --token $GITLAB_TOKEN
gitlab-runner run
```
