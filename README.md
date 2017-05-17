# Structurer

It is a CLI adaptation of the [Structurer App](https://code.tutsplus.com/articles/free-mac-utility-app-structurer--net-17153).

## Install

The script uses some tools:

 - curl
 - jq
 - unzip (optional)

## Usage

First you need to create a proper configuration file when you may create some aliases:

```
$ mkdir -p ~/.structurer
$ cat > ~/.structurer/structurer.json << EOF
{
    "aliases": [
        {
            "name": "MIT",
            "type": "url",
            "value": "https://raw.githubusercontent.com/kevinlebrun/documentalist/master/LICENSE"
        },
        {
            "name": "jquery",
            "type": "file",
            "value": "path/to/local/jquery.js"
        }
    ]
}
EOF
```

Note: If you map an archive (`.tar.gz` or `.zip`) to a directory, the archive will be extracted inside the directory.

Then you can generate any tries with `structurer`:

```
$ cat > structure << EOF
file.txt
path/file.txt
LICENSE:MIT
EOF
$ cat structure | structurer - dest
$ tree dest
dest
├── LICENSE
├── file.txt
└── path
    └── file.txt

1 directory, 3 files
```

## TODO

 - [ ] Write a proper documentation
 - [ ] Write complete test suite
 - [ ] Support `-h`
