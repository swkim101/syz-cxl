# syz-cxl

Minimal and naive support for fuzzing CXL.

1. Build kernel with `.config`
2. Apply syzkaller patch

```bash
git clone  https://github.com/google/syzkaller
cd syzkaller
git checkout 17d780d63fb22ce9f5928fb059d6dde009510d37
git am ../patch/*.patch
make -j8
mv ../cxl.json syzkaller/
./bin/syz-manager -config cxl.json
```