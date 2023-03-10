### Simple build environment
1. Install an Ubuntu (Server/Desktop) VM
2. Install NodeJS
  ```
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
  nvm install --lts
  ```
3. Install build tools
  ```
  sudo apt install build-essential
  ```
4. Install xPack (ref:https://xpack.github.io/dev-tools/arm-none-eabi-gcc/install/)
  ```
  mkdir mcHF
  cd mcHF
  npx xpm init
  npx xpm install @xpack-dev-tools/arm-none-eabi-gcc@latest --verbose
  ```
5. Append the arm-none-eabi into PATH
  ```
  export PATH=~/.local/xPacks/@xpack-dev-tools/arm-none-eabi-gcc/12.2.1-1.2.1/.content/bin:$PATH
  ```
6. Get the UHSDR source
  ```
  git clone https://github.com/df8oe/UHSDR.git
  ```
7. Compile the UHSDR
  ```
  cd UHSDR/mchf-eclipse
  make firmware
  # build for 512KB F4:
  # make BUILDFOR=F4-512KB firmware
  ```
