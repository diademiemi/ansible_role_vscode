# Ansible Role VSCode
This is an Ansible role that installs VSCode on Linux. It uses the Debian or RPM packages from Microsoft.  

Tested on Fedora 36 and Ubuntu 20.04, should work on any Linux distribution that the VSCode packages support.  
## Requirements

### Base requirements
Debian- or Red Hat based distribution.  

## Variables
| Variable | Default | Description |
|----------|---------|-------------|
| `vscode_user` | `{{ ansible_user_id }}` | User to install extensions for. |

## Installing extensions
To install extensions for VSCode, define the `vscode_extensions` variable.  
```yaml
vscode_extensions:
  - GitHub.copilot-nightly
  - GitHub.github-vscode-theme
```
