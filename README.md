# Important
The new version is more of a beta, you can find the original in the oldversions folder if this doesn't work out for you. Please report any issues.

# spsox

`spsox` is a simple Bash script that generates spectrograms from FLAC files using the `sox` command-line tool. It supports parallel processing, customizable spectrogram parameters, and recursive directory traversal.

---

## Features

- **Parallel Processing**: Utilizes multiple threads to process files concurrently.
- **Customizable Spectrograms**: Adjust the X-axis, Y-axis, and Z-axis resolutions for both zoomed and full spectrograms. As well as start time and duration.
- **Recursive Directory Traversal**: Process all `.flac` files in a directory and its subdirectories.
- **Logging**: Detailed logs are written to a timestamped log file for debugging and tracking progress.
- **Progress Tracking**: Displays real-time progress and a summary of processed files.

---

## Requirements

- **Bash**: The script is written in Bash and requires a Bash shell to run.
- **sox**: The `sox` command-line tool must be installed. You can install it using your package manager:
  - **Debian/Ubuntu**: `sudo apt install sox`
  - **Arch Linux**: `sudo pacman -S sox`
  - **macOS**: `brew install sox`

---

## Usage

### Basic Usage

    spsox

This will process all `.flac` files in the current directory using default settings. This is all most people will need to analyze the spectrograms.

### Options

| Option            | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| `-r`, `--recursive` | Process `.flac` files in the specified directory and all subdirectories.    |
| `-f`, `--force`     | Overwrite existing spectrogram files.                                       |
| `-q`, `--quiet`     | Suppress non-error output.                                                  |
| `-x`, `--x-axis`    | Set the X-axis resolution for the spectrogram (default: `500`).             |
| `-y`, `--y-axis`    | Set the Y-axis resolution for the spectrogram (default: `1025`).            |
| `-z`, `--z-axis`    | Set the Z-axis resolution for the spectrogram (default: `120`).             |
| `-h`, `--help`      | Display the help message and exit.                                          |
| `-v`, `--version`   | Display the script version and exit.                                        |

### Arguments

| Argument      | Description                                                                 |
|---------------|-----------------------------------------------------------------------------|
| `input`       | A directory containing `.flac` files or a single `.flac` file.              |
| `threads`     | Number of parallel threads to use (default: number of CPU cores).           |
| `start_time`  | Start time for the zoomed spectrogram (default: `1:00`).                    |
| `duration`    | Duration of the zoomed spectrogram (default: `0:02`).                       |

### Examples

1. **Process a Single File**:

        spsox /path/to/file.flac 12 0:20 0:05

   - Processes a single `.flac` file with 12 threads, starting at `0:20` and spanning `5` seconds.

2. **Process a Directory**:

        spsox /path/to/directory 8 3:00 0:05

   - Processes all `.flac` files in the specified directory with 8 threads, starting at `3:00` and spanning `5` seconds.

3. **Recursive Processing**:

        spsox -r /path/to/directory 4

   - Processes all `.flac` files in the directory and its subdirectories with 4 threads.

4. **Custom Thread Count Only**:

        spsox 6

   - Processes `.flac` files in the current directory with 6 threads.

---

## Output

- **Spectrograms**: Spectrogram images are saved in a `specs` folder within the same directory as the input `.flac` files.
  - **Zoomed Spectrogram**: `<filename>.zoomed.png`
  - **Full Spectrogram**: `<filename>.full.png`

- **Logs**: Logs are written to `/tmp/spsox_<timestamp>.log`.

---

## Notes

- The `start_time` and `duration` arguments must be in `HH:MM:SS` or `MM:SS` format.
- If `start_time + duration` exceeds the file length, the duration is adjusted automatically.
- Requires `sox` and `soxi` to be installed.

---

## License

This script is licensed under the GNU General Public License v3.0. See the [LICENSE](LICENSE) file for details.

---

## Author

- **Ewol**
- GitHub: [EwolBash](https://github.com/EwolBash)

---

## Contributing

Contributions are welcome! If you find a bug or have a feature request, please open an issue or submit a pull request.

---

## Acknowledgments

- Thanks to the developers of `sox` for providing such a powerful tool.
- Inspired by the need for a simple, customizable spectrogram generation script.

---

## Support

If you find this script useful, consider giving it a ⭐ on GitHub! 😊
