```sh
nix-env -iA cachix -f https://cachix.org/api/v1/install
```

https://docs.cachix.org/pushing#flakes
```sh
nix flake archive --json \
  | jq -r '.path,(.inputs|to_entries[].value.path)' \
  | cachix push whslabs
```
