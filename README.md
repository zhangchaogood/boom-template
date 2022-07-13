## Getting Started
### Checking out the sources
After cloning this repo, you will need to initialize all of the submodules  
```bash
cd boom-template
git reset --hard e8e93a1a1825567539de24b6aeead60ddf231a32
git rm boom
git clone https://github.com/riscv-boom/riscv-boom.git boom
cd boom && git reset --hard ea0ef4e135452f22bbe6abf5d98351bd22c846bc && cd ..
git submodule update --init
cd rocket-chip
git submodule update --init
cd riscv-tools
git submodule update --init
cd riscv-gnu-toolchain
git rm riscv-qemu
cd ../..
cd torture
vim .gitmodules(修改git://为https://)
git submodule sync
cd ../..
git submodule update --init --recursive
```
