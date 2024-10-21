# Ansible Role: Pip (for Python)

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

An Ansible Role that installs [Pip](https://pip.pypa.io) on Linux.

## Requirements

On RedHat/CentOS, you may need to have EPEL installed before running this role. You can use the `nholuong.repo-epel` role if you need a simple way to ensure it's installed.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    pip_package: python3-pip

The name of the packge to install to get `pip` on the system. For older systems that don't have Python 3 available, you can set this to `python-pip`.

    pip_executable: pip3

The role will try to autodetect the pip executable based on the `pip_package` (e.g. `pip` for Python 2 and `pip3` for Python 3). You can also override this explicitly, e.g. `pip_executable: pip3.6`.

    pip_install_packages: []

A list of packages to install with pip. Examples below:

    pip_install_packages:
      # Specify names and versions.
      - name: docker
        version: "1.2.3"
      - name: awscli
        version: "1.11.91"
    
      # Or specify bare packages to get the latest release.
      - docker
      - awscli
    
      # Or uninstall a package.
      - name: docker
        state: absent
    
      # Or update a package to the latest version.
      - name: docker
        state: latest
    
      # Or force a reinstall.
      - name: docker
        state: forcereinstall
    
      # Or install a package in a particular virtualenv.
      - name: docker
        virtualenv: /my_app/venv

## Dependencies

None.

## Example Playbook

    - hosts: all
    
      vars:
        pip_install_packages:
          - name: docker
          - name: awscli
    
      roles:
        - nholuong.pip

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
