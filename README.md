# private-docker-registry-fetcher
For interacting with the private Docker registry in a certain HTB box. Interacts using auth token system and Docker v2 API.

It obtains the name of a repo that the registry is hosting, then finds all tags for that repo, and checks the manifest of the tag it finds. After all that, it downloads all blobs that are shown in the manifest.

> A lot of this repo is specific to that one HTB box, so use with care. 



## Instructions

```
exploit.py [-h] IP Blob_Directory
```

- IP is the address of the target. HTTPS is assumed. Port numbers are also assumed.
- Blob_Directory is the relative path to the directory where you want all the blobs downloaded into



## Acknowledgement

The overall procedure was inspired by [this excellent walkthrough by 0xdf](https://0xdf.gitlab.io/2020/04/04/htb-registry.html#download-all-blobs)  for a previous HTB box. The code for downloading all blobs was adapted from [NotSoSecure's docker_fetch repo](https://github.com/NotSoSecure/docker_fetch). Details on the Docker registry v2 API's token mechanism were obtained [from here](https://github.com/distribution/distribution/blob/main/docs/spec/auth/token.md). Thank you all :clap:

