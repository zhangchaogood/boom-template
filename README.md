## Getting Started
### 1 
```bash
cd boom-template
git reset --hard e8e93a1a1825567539de24b6aeead60ddf231a32
git rm boom
git clone https://github.com/riscv-boom/riscv-boom.git boom
cd boom && git reset --hard ea0ef4e135452f22bbe6abf5d98351bd22c846bc && cd ..
git submodule update --init
```
### 2
```bash
cd rocket-chip
git submodule update --init
cd riscv-tools
git submodule update --init
cd riscv-gnu-toolchain
git rm riscv-qemu
cd ..
cd ..
```
