
# image-syncer [![image-sync](https://github.com/lim1202/image-syncer/actions/workflows/image-sync.yml/badge.svg)](https://github.com/lim1202/image-syncer/actions/workflows/image-sync.yml)
sync k8s.gcr.io docker images to dockerhub or aliyun registry use [aliyun image-syncer](https://github.com/AliyunContainerService/image-syncer) and github action!

## Getting Started

1. fork this repo, then create your self secrets:
```
Settings-->Secrets-->New Repository Secrets--> Add your DOCKERHUB_USERNAME and DOCKERHUB_PASSWORD key values.
```

2. add registry to `images:` that you want to sync:

format
```
auth:
  <src or destation registry url>
    username: USERNAME
    password: PASSWORD
images:
   <src registry>: <destation registry>
```

do not change USERNAME and PASSWORD ,it will be replaced by sed command

```yaml
auth:
  registry.hub.docker.com:
    username: USERNAME
    password: PASSWORD
images:
  quay.io/coreos/kube-rbac-proxy": quay.io/ruohe/kube-rbac-proxy,
  xxxx: xxxxx
```

3. check action logs

4. after synced, check your images
