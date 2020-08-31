# Package management

## Debian based system

### apt

*	`apt install` => install a package
*	`apt remove` => remove a package
*	`apt purge` => remove package and configurations
*	`apt update` => Refresh repository index
*	`apt upgrade` => Upgrade all upgradable packages
*	`apt autoremove` => Remove unwanted packages
*	`apt full-upgrade` => Upgrade package & auto-handle dependencies
*	`apt search` => Search for packages
*	`apt show` => Show package details.
*	`apt list` => List packages with criteria(installed, all available, upgradeable)
*	`apt edit-sources` => Edit the sources.list in the preferred editor.

### apt-get

*	`apt-get install` => install a package
*	`apt-get remove` => remove a package
*	`apt-get purge` => remove package and configurations
*	`apt-get update` => Refresh repository index
*	`apt-get upgrade` => Upgrade all upgradable packages
*	`apt-get autoremove` => Remove unwanted packages
*	`apt-get dist-upgrade` => Upgrade package & auto-handle dependencies
*	`apt-cache search` => Search for packages
*	`apt-cache show` => Show package details.

### dpkg

## Universal Linux Package Mangement

### snap

*	`snap version` => show the snap version
*	`snap find [pkgname]` => find the pkgname details
*	`snap install [pkgname]` => install pkgname
*	`snap list` => show installed packages
*	`snap info [pkgname]` => show pkgname details, and channels(stable, candidate, beta, edge)
*	`snap install [pkgname] --channel=[cnlname]` => install pkgname from cnlname channel
*	`snap refresh [pkgname] --channel=[cnlname]` => change the channel of currently installed pkgname
*	`sudo snap refresh --list` => check if updates are available
*	`sudo snap remove [pkgname]` => remove the package pkgname