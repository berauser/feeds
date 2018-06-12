Additional openwrt/lede feeds

Add line ```src-git additional_feeds https://github.com/berauser/feeds.git``` to
```feeds.conf.default``` and run ``` ./script/feeds update -a && ./script/feeds install -a```