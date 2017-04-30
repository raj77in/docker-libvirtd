# docker-libvirtd
Running libvirtd in docker
Works in Fedora 25 and F26

```bash
docker run \
   --privileged \
   --detach=true \
   --name libvirtd \
  alectolytic/libvirtd
```

Or you can specify init to be run as command in following fashion.

```bash
docker run  --name libvirtd \
	   --privileged -d -e 'container=docker' \
	   -v /var/lib/libvirt/:/var/lib/libvirt/ \
	   -v /sys/fs/cgroup:/sys/fs/cgroup:rw \
	   -p 16509:16509 raj77in/libvirtd /usr/sbin/init
```

Thanks to Arun Babu Neelicattu [Github repo](https://github.com/abn/dockerfiles)
