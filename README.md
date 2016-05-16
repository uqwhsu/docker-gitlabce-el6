# GitLab Docker images

## Introduction

This is adapted from official GitLab Docker images based on Ubuntu to use CentOS 6 base image, while follow as close to official Omnibus package install as possible.

- [Omnibus CentOS 6 install guide](https://about.gitlab.com/downloads/#centos6)
- [Official GitLab CE docker repo](https://gitlab.com/gitlab-org/gitlab-ce/tree/master)

## Complete Example

```bash
sudo docker build -t uqwhsu/gitlab-ce --rm=true --force-rm=true .

sudo docker run --detach \
    --hostname gitlab.example.com \
    --publish 443:443 --publish 80:80 --publish 22:22 \
    --name gitlab \
    --restart always \
    --volume /srv/gitlab/config:/etc/gitlab \
    --volume /srv/gitlab/logs:/var/log/gitlab \
    --volume /srv/gitlab/data:/var/opt/gitlab \
    uqwhsu/gitlab-ce
```
After starting the container you can visit <http://localhost/> or <http://192.168.59.103> if you use boot2docker.

---

## Additional Information

Please see: [Official GitLab Docker images guide](https://gitlab.com/gitlab-org/omnibus-gitlab/blob/master/doc/docker/README.md)

