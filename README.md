# OpenRISC_Tool 
OpenRISC_Tool used for OpenRISC simulate，compile and debug, I have installed and tested in ubuntu 14.04 LTS(32bit) 
Here is the steps 
#Automatic build
1、prepare for build
  
  $cd ~
  
  $git clone https://github.com/lx324310/OpenRISC_Tool.git openrisc-tool
  
  $cd openrisc-tool
  
  $make install
  
#Manual build
1、build a working directory
  
  $mkdir ~/openrisc-tool
  
#OpenRISC debug tools install
We can use OpenOCD or advance_debug_bridge(software) to debug OpenRISC via advance_debug_bridge(Hardware),however advance_debug_bridge(S) download speed is very slow when i used on altera FPGA(4KB/S),xilinx FPGA(268B/s),yet OpenOCD download speed reach 54KB/s on altera FPGA. So i will to use OpenOCD,

OpenOCD install
1、preparing for install
  
  $sudo apt-get install -y pkg-config libusb-1.0-0-dev libtclcl1-dev libftdi-dev
  
2、Getting the Repo and bootstrap
  
  $cd ~/openrisc-tool
  
  $git clone https://github.com/lx324310/openocd.git
  
  $cd openocd
  
  $./bootstrap

3、Configure and build for a target running on an Altera FPGA and jtag vpi for sim
  
  $./configure --enable-usb_blaster_libftdi --enable-adv_debug_sys --enable-jtag_vpi --enable-maintainer-mode

  $make 
  
  $make install

advance debug bridge install

#OR1ksim install
OR1Ksim is a simulator of openrisc,you can build you own OR1200 or SOC based on OR1200
(Pay attention,Before you install GNU toolchain you must install or1ksim)
  
1、Getting the Repo and config

  $cd openrisc-tool
  
  $git clone https://github.com/lx324310/OR1Ksim.git or1ksim
  
  $cd or1ksim
  
  $mkdir or1ksim-build
  
  $cd or1ksim-build
  
  $../or1ksim/configure --program-prefix=or1k-elf- --prefix=/opt/or1ksim
  
2、build and install

  $make
  
  $sudo make install

3、set env parameter
  
  $echo "#OR1ksim tools" >>~/.bashrc
  
  $echo "PATH=\$PATH:/opt/or1ksim/bin">>~/.bashrc
  
  $source ~/.bashrc
  
#OpenRISC GNU Toolchain
(OR32 or OR1K,OR32 is the older for OR1K,mkg-soc and minsoc is based on OR32 )

OR32 GNU toolchain install





  
