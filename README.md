# petalinux_analogdevice
1. petalinux-create --type project --template zynq --name lnx

2. cd lnx
3. petalinux-config --get-hw-description=../
4. add layer in Yoctor:

${proot}/project-spec/meta-adi-core
${proot}/project-spec/meta-adi-xilinx

5. echo "KERNEL_DTB=\"zynq-zc706-adv7511-ad9625-fmcadc2\"" >> project-spec/meta-user/conf/petalinuxbsp.conf
verify in : /project-spec/meta-user/conf must have : KERNEL_DTB="zynq-zc706-adv7511-ad9625-fmcadc2"  not KERNEL_DTB="zc706-adv7511-ad9625-fmcadc2" --> this main reason of error: "Failed to add user layer: /home/thanh1804/hdl-hdl_2019_r2/linux/lnx2/project-spec/meta-adi/meta-adi-core"

6. petalinux-build


