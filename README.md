```console
% nixops create -s state.nixops network.nix
% nixops deploy -s state.nixops  --show-trace
% nixops ssh -s state.nixops restream
[root@restream:~]# echo '{"rtmp://localhost/pub_secret/stream": ["rtmp://localhost/norestream/stream"]}' > /tmp/targets
[root@restream:~]# stream-bunny # test
```

## macos

```console
sudo $(nix-store --realise $(nix-instantiate -A eval.config.extra.nginx.script  ./network.nix ))
```
