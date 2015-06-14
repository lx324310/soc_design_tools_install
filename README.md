# OpenRISC_Tool 
OpenRISC_Tool used for OpenRISC simulate，compile and debug, I have installed and tested in ubuntu 14.04 LTS(32bit) 
Here is the steps 

#OpenRISC debug tools install
(OpenOCD or advance_debug_bridge via test advance_debug_bridge have some bugs,the OpenOCD test well on board verification but I don't test simulate by OpenOCD) 

OpenOCD install
1、preparing for install
  
  $sudo apt-get install -y pkg-config libusb-1.0-0-dev libtclcl1-dev libftdi-dev
  
2、Getting the Repo and bootstrap
  
  $cd ~
  
  $git clone https://github.com/lx324310/openocd.git
  
  $cd openocd
  
  $./bootstrap

3、Configure and build for a target running on an Altera FPGA
  
  $./configure --enable-usb_blaster_libftdi --enable-adv_debug_sys --enable-altera_vjtag --enable-maintainer-mode

  $make 
  
  $make install

advance debug bridge install

#OR1ksim install
OR1Ksim is a simulator of openrisc,you can build you own OR1200 or SOC based on OR1200 

1、build a working directory
  
  $cd ~
  
  $mkdir openrisc-tool
  
2、Getting the Repo and config

  $cd openrisc-tool
  
  
  $git clone https://github.com/lx324310/OR1Ksim.git or1ksim
  
  $cd or1ksim
  
  $mkdir or1ksim-build
  
  $cd or1ksim-build
  
  $../or1ksim/configure --program-prefix=or1k-elf- --prefix=/opt/or1ksim
  
3、build and install

  $make
  
  $sudo make install

4、set env parameter
  
  $echo "#OR1ksim tools PATH" >>~/.bashrc
  
  $echo "export PATH=$PATH:/opt/or1ksim/bin"
  
#OpenRISC GNU Toolchain
(OR32 or OR1K,OR32 is the older for OR1K)

OR1Ksim install


OR32 GNU toolchain install





  
