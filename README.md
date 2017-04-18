Ansible role java-oracle
========================

[![Build Status](https://travis-ci.org/nwoetzel/ansible-role-java-oracle.svg?branch=master)](https://travis-ci.org/nwoetzel/ansible-role-java-oracle)

An [Ansible](http://www.ansible.com) role to install the  Oracle Java Development Kit or Java Runtime Environment. 7, [8](http://www.oracle.com/technetwork/java/javase/downloads/index.html) and [9 early-access](https://jdk9.java.net/download/) are supported.

## DISCLAIMER

By installing any version of this role you have accepted the [Oracle Binary Code License Agreement for Java SE](http://www.oracle.com/technetwork/java/javase/terms/license/index.html) and the [Early Adopter Development License Agreement for Java SE](http://www.oracle.com/technetwork/licenses/ea-license-noexhibits-1938914.html).

## Description

This ansible role is for installing java oracle by downloading the tar and unpacking it into a software folder under the users home.
It should work for either Debian or Ubuntu, it has been tested for Ubuntu only.
It does not handle MacOS or Windows (yet).

For all settings, look into the defaults folder.

## Dependencies

- ansible >= 2

## Role Variables

All defaults are documented also in the [defaults](defaults/main.yml) file.

| variable | required | default | description |
|--:|:-:|:-:|:--|
| java_product | yes | - | one of jre or jdk |
| java_version | yes | - | 7,8 (9 in the future) |
| java_shell_profile | no | false | add the JAVA_HOME with installation path to the user's shell profile? |
| java_download_folder_remote | no | - | when set, the file is downloaded to the installation host |
| java_update | no | set by this [role](vars/main.yml) | The latest update version defined in that role is used. If this is not up to date (newer is required), or an older version is desired, set this. |
| java_build | no | set by this [role](vars/main.yml) | e.g. b15, is usually part of the filename to download |
| java_arch | no | derived from machine fact and converted [in](tasks/set_vars.yml) | e.g. x86, x86_64 |
| java_os | no | derived from machine fact and converted [in](tasks/set_vars.yml) | e.g. linux |

## Facts

| variable | description |
| java_install_dir | the installation directory used for e.g. JAVA_HOME |

## License

[GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)
