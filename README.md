# FileSec

**FileSec** is not a dependency scanner, it is an open-source grep command which scans codebases for specific vulnerable packages and service calls, ensuring comprehensive protection against known threats. It helps developers identify and mitigate potential security risks in their codebase.

While dependency scanners provide robust security scanning for dependencies, FileSec can help to defend against inline vulnerabilities within your codebase.

## Usage

1. Open a terminal and navigate to your code repository.
2. Run the `filesec` command, passing in the blacklisted dependencies to search for, e.g:

```bash
echo "polyfill.js,polyfill.io" | tr ',' '\n' | grep -r -F -f - --include=\*.{json,js,html,css,php} .
```

The command will output any lines containing the blacklisted dependencies (for example, polyfill.js and polyfill.io) from the specified file types:

```bash
./file-1.js:polyfill.js
./file-2.php:polyfill.io
```

On Windows, [Git Bash](https://git-scm.com/downloads) provides a Unix-like environment that includes grep, tr, and other essential tools, making it possible to run FileSec.

## Contributing
Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request on the [GitHub repository](https://github.com/filesec-labs/filesec).

## License
FileSec is intellectual property of FileSec Labs released under the MIT License.
