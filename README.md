Thank you to [Dirk Lemstra](https://github.com/dlemstra/code-sign-action) and [Dana Prajea](https://github.com/Dana-Prajea/code-sign-action). 

# Code sign a file

This action signs files that are supported by `signtool.exe` with a code signing certificate that takes in a password. This action only works on Windows and that means it should run on `windows-latest`.

## Inputs

### `certificate`

**Required** The base64 encoded certificate.

### `password`

**Required** Certificate Password.

### `folder`

**Required** The folder that contains the files to sign.

### `recursive`

**Optional** Recursively search for files.

### `timestampUrl`

**Optional** Url of the timestamp server.  Default is 'http://timestamp.digicert.com'

## Example usage

```
runs-on: windows-latest
steps:
  uses: sproctor/code-sign-action@v1
  with:
    certificate: '${{ secrets.CERTIFICATE }}'
    password: '${{ secrets.PASSWORD }}'
    folder: 'files'
    recursive: true
```
