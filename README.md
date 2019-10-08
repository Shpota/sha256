A shortcut script that helps verify sha256 sums faster
======================================================

The script is based on `sha256sum` utility and allows to compare
SHA 256 sums without downloading a file with the sum.

## How to install
- **Option 1**: Download the [sha256](sha256) script and add it to your `PATH` variable.

- **Option 2**: Add the following function to your `.bashrc` or `.zshrc` file:
  ```shell script
  sha256() {
      echo "$1 $2" | sha256sum --check
  }
  ```
  
Make sure you have [sha256sum utility](http://www.gnu.org/software/coreutils/sha256sum) installed.

## How to use
You can compare SHA 256 sums in the following way:
```shell script
sha256 <expected-sha-256-sum> <name-of-the-file>
```

## Examples
```shell script
sha256 94f874037b82ea5353f4061e543681a0e79657f787437974214629af8407d124 go1.13.1.linux-amd64.tar.gz
```
The output if the sums match:
```
go1.13.1.linux-amd64.tar.gz: OK
```
The output if the sums do not match:
```shell script
go1.13.1.linux-amd64.tar.gz: FAILED
```