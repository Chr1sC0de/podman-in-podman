
```bash
(cd rocky-podman-9 && podman build -t rocky-podman-9 .)
(cd rocky-neovim-devcontainer && podman build -t rocky-neovim-devcontainer .)
# rootless in rootless
podman run -itd --security-opt label=disable --user podman --device /dev/fuse localhost/rocky-podman-9 
# rootful in rootful
podman run -itd --cap-add=sys_admin,mknod --device=/dev/fuse --security-opt label=disable localhost/rocky-podman-9
```

```bash
(cd ubuntu-podman && podman build -t ubuntu-podman .)
# rootless in rootless, couldn't get this working
podman run -itd --security-opt label=disable --user podman --device /dev/fuse localhost/ubuntu-podman
# rootful in rootful
podman run -itd --cap-add=sys_admin,mknod --device=/dev/fuse --security-opt label=disable localhost/ubuntu-podman
```
# podman-in-podman
# podman-in-podman
# podman-in-podman
