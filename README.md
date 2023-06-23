The base `zarf.yaml` will import `sibling`, which imports `child`, which imports `leaf`. `leaf` is the only import that will have its file paths fixed to be relative to the import path.

```
kind: ZarfPackageConfig
metadata:
  name: parent
components:
- name: file
  required: true
  files:
  - source: leaf/lfile.txt
    target: lfile.txt
  - source: cfile.txt
    target: cfile.txt
  - source: sfile.txt
    target: sfile.txt
  - source: file.txt
    target: file.txt
```
