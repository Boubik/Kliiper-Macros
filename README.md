# Klipper-Settings
This repository contains a collection of setting for Klipper, a 3D printer firmware that runs on a Raspberry Pi and controls the printer via USB. Klipper allows you to define custom G-code commands and scripts that can be executed from the printer’s LCD menu, web interface, or slicer.

# Installation
To use these macros, you need to have Klipper installed and configured on your Raspberry Pi and 3D printer. You can follow the official installation guide.
- Add this repository as a git submodule to your klipper_config folder on your Raspberry Pi by running the following commands:
  ```terminal
  cd ~/
  git clone https://github.com/Boubik/Kliiper-Settings.git Boubik-Settings
  ln -s ~/Boubik-Settings/configs printer_data/config/Boubik-Settings
  cp ~/Boubik-Settings/Boubik-Settings.cfg ~/printer_data/config/Boubik-Settings.cfg
  ```

- Add the following section to your moonraker.conf file to enable Moonraker to automatically update this repository:
  ```config
  [update_manager Boubik-Settings]
  type: git_repo
  primary_branch: master
  path: ~/Boubik-Settings
  origin: https://github.com/Boubik/Kliiper-Settings.git
  is_system_service: False
  ```

- Restart Moonraker.

- To enable the macros, you need to edit your printer.cfg file and include the macros.cfg file from this repository. For example, you can add the following line to your printer.cfg file:
  ```config
  [include Boubik-Settings.cfg]
  ```

# License
[MIT](LICENSE)

# Credits
These macros are based on or inspired by some of the examples from the official Klipper documentation and the Klipper community. I would like to thank them for their work and contributions.

