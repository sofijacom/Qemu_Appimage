# Qemu_Appimage
########################################################################
<br> Thank you for sharing this project across the internet! <br/>
<br> If you like it don't forget to give an star. <br/>
<br> By the way this is an unofficial project. <br/>
########################################################################


<br> This is a Prove of the concept that is possible to run a virtual machine from an Appimage. <br/>
<br> What is the goal? <br/>
<br> To run QEMU a virtual machine emulator from this cantrainer. <br/>

which architectures are possible to run ussing this appimage? almost all of then which is supported by QEMU.
In this repository you may find a text file with examples for ussing This QEMU AppImage, of course it's all in portuguese, but no need worries... those commands are the same for every single use o QEMU.
if you had doubts about the use you can find me in Telegram: @zainotel.

<br> useful commands! <br/>

<br> this one bellow creat an hard drive <br/>

<br> ./QEMU-x86_64.AppImage qemu-img create -f qcow2 windows10.qcow2 30G <br/>

<br> this other example boot the iso file <br/>

<br> ./QEMU-x86_64.AppImage qemu-system-x86_64 -enable-kvm -cpu host -smp cores=2 -m 4G -name 'Manjaro' -boot d -hda ~/Documentos/Manjaro.qcow2 -cdrom ~/Documentos/manjaro-gnome-21.3.7-220816-linux515.iso <br/>

<br> attention if you're using the version stable or the one which was build from the source you must use this command <br/>

<br> ./QEMU-x86_64.AppImage qemu-system-x86_64 -enable-kvm -M q35 -vga virtio -display gtk,gl=on -cpu host -smp cores=2 -m 1G -name 'teste' -boot d -hda ~/Downloads/organizar/windows10.qcow2 -cdrom ~/Documentos/AppImage/TinyCorePure64-14.0.iso <br/>

<br> the option -vga virtio -display gtk,gl=on will enable the gtk interface instead of vnc or if you didn't like gtk window you can change to sdl. the network is working normaly. <br/>

<br> the audio is working use this command to get audio outoput in HDMI monitor or TV <br/>

<br> ./QEMU-git.AppImage qemu-system-x86_64 -enable-kvm -M q35 -vga virtio -display gtk,gl=on -cpu host -smp cores=2 -m 1G -name 'teste' -boot d -hda ~/Downloads/organizar/windows10.qcow2 -cdrom ~/Downloads/organizar/bodhi.iso -device ich9-intel-hda,addr=1f.1 -audiodev pa,id=snd0 -device hda-output,audiodev=snd0 <br/>
