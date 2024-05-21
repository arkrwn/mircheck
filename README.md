
# Mircheck - Fastest Mirror Selector for Ubuntu and it's derivatives

This script helps you find the fastest mirror for your Ubuntu and it's derivatives and generates a `sources.list` file accordingly. 
It downloads the `Release` file from each mirror to measure the speed and identifies the fastest one.

## Requirements

- Python 3.6 or higher
- `requests` library

## Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/arkrwn/mircheck.git
   cd mircheck
   ```

2. **Install the required libraries:**
   ```sh
   pip install requests
   ```

## Usage

```sh
python3 mircheck.py [options] <distribution> <country>
```

### Positional Arguments

- `distribution`: Distribution code name (e.g., jammy, bionic).
- `country`: Country code or name.

### Options

- `-a, --arch ARCH`: Specify architecture (e.g., amd64, arm64). Default is the architecture of the current machine.
- `-s, --sources`: Include `deb-src` lines in the generated `sources.list`.
- `-o, --outfile OUTFILE`: Output file for `sources.list`. Default is `./sources.list`.
- `-n, --nonfree`: Include non-free section in the generated `sources.list`.
- `-d, --distribution_type {stable, testing, unstable, experimental, release_codename, sid}`: Specify which distribution of Debian to use. Default is `stable`.

### Examples

1. **Find the fastest mirror for Ubuntu `jammy` in Indonesia and save to the current directory:**
   ```sh
   python3 mircheck.py jammy id
   ```

2. **Find the fastest mirror for Debian `stable` in Germany and include source lines:**
   ```sh
   python3 mircheck.py stable germany -s
   ```

3. **Find the fastest mirror for Ubuntu `bionic` in the USA and save to a custom path:**
   ```sh
   python3 mircheck.py bionic us -o /path/to/custom/sources.list
   ```

## Output

The script will test each mirror's speed and display the results in kilobytes per second (KB/s). It will identify the fastest mirror and generate a `sources.list` file with the appropriate entries.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Contributing

Feel free to submit issues and pull requests. For major changes, please open an issue first to discuss what you would like to change.

## Acknowledgements

- The `requests` library for handling HTTP requests.
- The Ubuntu and Debian communities for providing mirror lists.

