# ZMK fingerpunch controllers

This is a ZMK module that allows you to build any keyboard shield using a fingerpunch controller.

## Using this module

To include the module, you'll need to add it to your zmk-config `config/west.yml`

It should look something like what's shown below. I've commented out things that you probably already have in the `config/west.yml`. You just need to add the parts that are uncommented.

```
manifest:
  remotes:
    # You'll likely have this already with your preferred ZMK version
    # - name: zmkfirmware
    #   url-base: https://github.com/zmkfirmware
    - name: sadekbaroudi
      url-base: https://github.com/sadekbaroudi
  projects:
    # You'll likely have this already with your preferred ZMK version
    # - name: zmk
    #   remote: zmkfirmware
    #   revision: main
    #   import: app/west.yml
    - name: zmk-fingerpunch-controllers
      remote: sadekbaroudi
      revision: main
      import: config/deps.yml
```

Once you've done that, you can use any of the controllers (boards) in this repository, along with any VIK module that you have connected to it. For example, here is an example `build.yml`:

```
---
include:
  - board: vikoto
    shield: <YOUR_KEYBOARD_NAME> vik_cirque_spi
```

The above contents will build your keyboard shield, using the vikoto as a controller, with an attached cirque trackpad.

## Examples

For a whole list of examples of this, please see the [zmk-fingerpunch-keyboards](https://github.com/sadekbaroudi/zmk-fingerpunch-keyboards) repository.