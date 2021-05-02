# Raspberry Pi Project Customizations

## Purpose
This document serves as a reference for customizing an OS image of Raspberry Pi
for use in a production project. Although this document focuses on Raspberry Pi,
these topics can apply to any project which uses an operating system built on
the Linux kernel. Topics covered here include:

### System Look and Feel
How does it "feel" to use your project? Has it been described as "janky?" We'll
look at how to put some polish on your project so users will walk away feeling
like they just used a million dollar piece of software, even if it is held
together with tooth picks and string.

### Security Concerns
Security in the IoT industry is a hot topic. Is your project public facing? Is
it expected to interact with users unattended? We'll discuss options for
hardening your projects underlying system to help prvent some unwanted security
situations.

## Boot Sequence
When starting a project using a Raspberry Pi you may not put much thought in to
the final presentation of your project. Often projects will ship (or at least
soft ship) with things like kernel boot messages still enabled. For some
projects this is an aesthetic choice, but for others it can turn users away
thinking "this feels unfinished." Here we will describe how to set up your
Raspberry Pi's boot sequence to present its best face to your users.

### Kernel Boot Messages
#### Disable kernel boot messages
Open /boot/cmdline.txt

```
# nano /boot/cmdline.txt
```

Add these command line options

```
quiet splash
```

#### Disable Raspberry Pi rainbow boot image
Open /boot/config.txt

```
# nano /boot/config.txt
```

Towards the bottom of the file, under the `[all]` section, add this line:

```
disable_splash=1
```

#### Adding a splash logo
