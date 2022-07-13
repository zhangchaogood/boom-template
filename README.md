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
### Building the tools
The tools repo contains the cross-compiler toolchain, frontend server, and proxy kernel, which you will need in order to compile code to RISC-V instructions and run them on your design. There are detailed instructions at https://github.com/riscv/riscv-tools. But to get a basic installation that will work with BOOM, just the following steps are necessary.
```bash
# You may want to add the following two lines to your shell profile
export RISCV=/path/to/install/dir
export PATH=$RISCV/bin:$PATH

cd boom-template
./scripts/build-tools.sh
```
### Compiling and running the Verilator simulation
To compile a BOOM simulator, run ```make``` in the "verisim" directory. This will elaborate the BoomConfig from the boom.system project.
```bash
cd verisim
make
```
