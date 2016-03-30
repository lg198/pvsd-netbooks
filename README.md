# pvsd-netbooks

This outlines the process of installing the PVSD Netbook image onto a single netbook.

## Clone the git repository

The install scripts are stored in a git repository. Run `git clone https://github.com/lg198/pvsd-netbooks.git` to clone it into a folder named `pvsd-netbooks`.

## Create the USB

You'll need an empty USB stick. It should be at least 2 GB for safety.

### Find the USB's "name"

The USB will have some path `/dev/sd?`, where `?` is a letter. You can determine which one it is by running `sudo fdisk -l`. Its 'name' is this path.

### Generate the ISO

Inside the `pvsd-netbooks` directory, run `./download_image.sh`. It might take a while.

When that is finished, run `sudo ./preseed.sh`. It will generate a lot of output.

When that is finished, run `sudo dd if=debian_patched.iso of=/dev/sd?`, where the `?` creates the USB "name" you found above. Chances are, its not `/dev/sda`. In fact, DO NOT use that. If you do, you'll overwrite your computer's hard drive!
