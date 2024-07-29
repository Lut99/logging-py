# LOGGING
A small Python library for standardising the same logging functions I keep writing for every script.


## Installation
Simply clone the repo into your project:
```sh
git clone https://github.com/Lut99/logging-py ./logging
```
or, if you want to be able to stay up-to-date:
```sh
git submodule add https://github.com/Lut99/logging-py ./logging
```

(don't forget to clone your own repository with `git clone --recursive` if you do)


## Usage
Then, you can add:
```python
import logging
```
at the top of your file.

The following functions are exposed:
- ```python
  def pdebug(text: str, end: str = '\n', use_colour: Optional[bool] = None, file: TextIOWrapper = sys.stderr)
  ```
- ```python
  def pinfo(text: str, end: str = '\n', use_colour: Optional[bool] = None, file: TextIOWrapper = sys.stderr)
  ```
- ```python
  def pwarn(text: str, end: str = '\n', use_colour: Optional[bool] = None, file: TextIOWrapper = sys.stderr)
  ```
- ```python
  def perror(text: str, end: str = '\n', use_colour: Optional[bool] = None, file: TextIOWrapper = sys.stderr)
  ```

All of them have the same behaviour and arguments (roughly), except that the log levels (and therefore styling) of the statements varies.
- `text`: The message to display.
- `end`: Something to print at the end of the message. By default, this is a newline.
- `use_colour`: Whether to use colour or not. Use `None` to try and deduce it automagically (default: `None`).
- `file`: The file on which to write the message. Defaults to stdout for `pdebug` and `pinfo`, defaults to stderr for `pwarn` and `perror`.

Then the script also exposes:
```python
def set_debug(enable: bool)
```
which allows one to control whether `pdebug()` does anything. By default, does not print anything unless `set_debug(True)` is called.


## Contribution
Feel free to contribute to the script! Either raise [an issue](/Lut99/logging-py/issues) or create [a pull request](/Lut99/logging-py/pulls).


## License
This project is licensed under Apache 2.0. See [LICENSE](./LICENSE) for more details.
