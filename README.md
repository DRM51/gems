# DRM51 gems

A Bundler source for DRM51's builds of gems we maintain forks of. No token
is needed.

```ruby
source "https://drm51.github.io/gems" do
  gem "mini_racer", "0.22.2.1"
end
```

Gems not listed here (libv8-node 24.x, for example) still come from
rubygems.org through the Gemfile's main `source`.

| Gem | Fork | Changes |
|---|---|---|
| mini_racer | [DRM51/mini_racer](https://github.com/DRM51/mini_racer) (branch `drm51`) | [CHANGELOG](https://github.com/DRM51/mini_racer/blob/drm51/CHANGELOG) |

## Versions

DRM51 builds add a numeric segment that upstream never uses: mini_racer
`0.22.2.1` is upstream 0.22.2 plus our build 1, and libv8-node
`26.12.1.0.1` is upstream's 26.12.1.0 numbering plus our build 1. Letters
are avoided on purpose, since RubyGems treats them as prereleases and
`~>` requirements would skip them.

## Publishing

1. Tag the fork (e.g. `v0.22.2.1`). Its release workflow tests the tagged
   commit, builds the gem and attaches it and `SHA256SUMS` to a GitHub
   release.
2. Add the asset URL and its sha256 to `gems.txt` here and push. The Pages
   workflow downloads every listed gem, checks its hash and rebuilds the
   index.
