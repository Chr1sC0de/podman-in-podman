# podman-in-podman

## Rocky Linux

```bash
(cd rocky-podman-9 && podman build -t rocky-podman-9 .)
# rootless in rootless
podman run -it --security-opt label=disable --user podman --device /dev/fuse localhost/rocky-podman-9 
# rootful in rootful
podman run -it --cap-add=sys_admin,mknod --device=/dev/fuse --security-opt label=disable localhost/rocky-podman-9
```

## Ubuntu Podman

```bash
(cd ubuntu-podman && podman build -t ubuntu-podman .)

# rootless in rootless
podman run -it --replace --name ubuntu-podman --user ubuntu --device /dev/fuse localhost/ubuntu-podman

# rootful in rootful
podman run -it --cap-add=sys_admin,mknod --device=/dev/fuse --security-opt label=disable localhost/ubuntu-podman
```


## Ubuntu Podman

```bash
(cd ubuntu-podman-2 && podman build -t ubuntu-podman-2 .)

# rootless in rootless
podman run -it --replace --name ubuntu-podman-2 --user ubuntu --device /dev/fuse localhost/ubuntu-podman-2

# rootful in rootful
podman run -it --cap-add=sys_admin,mknod --device=/dev/fuse --security-opt label=disable localhost/ubuntu-podman
```

## Resources

- https://samuel.forestier.app/blog/security/podman-rootless-in-podman-rootless-the-debian-way
- https://www.redhat.com/en/blog/podman-inside-container
- https://github.com/containers/image_build/tree/main/podman
