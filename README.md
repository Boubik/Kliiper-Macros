# Klipper-Macros
This repository contains a collection of macros for [Klipper], a 3D printer firmware that runs on a Raspberry Pi and controls the printer via USB. Klipper allows you to define custom G-code commands and scripts that can be executed from the printer’s LCD menu, web interface, or slicer.

# Installation
To use these macros, you need to have Klipper installed and configured on your Raspberry Pi and 3D printer. You can follow the official installation guide.
- Add this repository as a git submodule to your klipper_config folder on your Raspberry Pi by running the following commands:
  ```terminal
  cd ~/klipper_config
  git submodule add https://github.com/Boubik/Kliiper-Macros.git Boubik-Macros
  ```

- Add the following section to your moonraker.conf file to enable Moonraker to automatically update this repository:
  ```config
  [update_manager boubik-macros]
  type: git_repo
  primary_branch: master
  path: ~/Boubik-Macros
  origin: https://github.com/Boubik/Kliiper-Macros.git
  ```
- Restart Moonraker by running the following command on your Raspberry Pi:
  ```terminal
  sudo service moonraker restart
  ```
- To enable the macros, you need to edit your printer.cfg file and include the macros.cfg file from this repository. For example, you can add the following line to your printer.cfg file:
  ```config
  [include Boubik-Macros/macros.cfg]
  ```

# License
[MIT](LICENSE)

# Credits
These macros are based on or inspired by some of the examples from [the official Klipper documentation] and [the Klipper community]. I would like to thank them for their work and contributions.

