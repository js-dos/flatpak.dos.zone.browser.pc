```
        const child = spawn("flatpak-spawn", 
            ["-v", "--directory=" + data, cmd, port + ""], { cwd: data });
        console.log("backend cmd:", "flatpak-spawn",
                ["-v", "--directory=" + data, cmd, port + ""], 
                "directory:", data, "child:", child.pid);
```
# Flatpak

```
DEBUG=electron-forge:*,electron-installer-flatpak*,flatpak-bundler*,flatpak-builder* yarn run make --targets "@electron-forge/maker-flatpak"
```

Useful commands:
```
flatpak remove zone.dos.browser.pc && \
flatpak install --user ./out/make/flatpak/x86_64/zone.dos.browser.pc_stable_x86_64.flatpak

flatpak run zone.dos.browser.pc
flatpak run --command=sh zone.dos.browser.pc 
```

Generate sources:

```
~/.local/bin/flatpak-node-generator yarn yarn.lock --electron-node-headers
```

Build locally:

```
flatpak-builder build --install-deps-from=flathub --force-clean --user --install dos.zone.Browser.yaml
```