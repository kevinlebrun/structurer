# Structurer

It is a CLI adaptation of the [Structurer App](https://code.tutsplus.com/articles/free-mac-utility-app-structurer--net-17153).

## Install

The script uses some tools:

 - curl
 - jq
 - unzip (optional)

## Usage

```
$ cat > structure << EOF
file.txt
path/file.txt
EOF
$ cat structure | structurer dest -
$ tree dest
```

## TODO

 - [ ] Write a proper documentation
 - [ ] Write complete test suite
 - [ ] Support `-h`
