# Intune for Linux

Works for me on Debian Sid (on top of `dm-crypt` and LUKS) as of 2022-03-24. YMMV.

## Dependencies

1. `systemd` (>= 2??)
2. `systemd-container`
3. `debootstrap`
4. `mkosi` (`sudo pip3 install git+https://github.com/systemd/mkosi.git` or see [here](https://github.com/systemd/mkosi))

## Configure

1. In `mkosi.default` modify `Password=` and `[Host]` section (optional).
2. In `mkosi.prepare` modify `HOSTNAME=` (optional).
3. In `mkosi.postinst` modify `UID=`, `GID=`, `HOME=` and `USER=` (**required**).
4. `mkosi.nspawn` will probably work as is (you can add your own binds here, e.g. `$HOME/Desktop`).

## Usage

1. Run `sudo mkosi boot` (in repository root) and wait (use `mkosi -f` to "reset" the image).
2. Log in with your `$USER`.
3. Run `intune-portal` and follow the instructions.
4. Run `microsoft-edge` and be brave.

## Troubleshooting

TODO
