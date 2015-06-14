# OpenRISC_Tool 
OpenRISC_Tool used for OpenRISC simulate，compile and debug, I have installed and tested in ubuntu 14.04 LTS(32bit) 
Here is the steps 

#OpenOCD install
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
  
