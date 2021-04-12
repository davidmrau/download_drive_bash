# Download File from Google Drive via Command Line / Bash

```
fileId=$1
fileName=$2
curl -sc cookie "https://drive.google.com/uc?export=download&id=${fileId}" > /dev/null
code="$(awk '/_warning_/ {print $NF}' cookie)"
curl -Lb cookie "https://drive.google.com/uc?export=download&confirm=${code}&id=${fileId}" -o ${fileN
ame}
```

Pass the `fileid` from the gdrive link and determine the `filename` that it will be saved to.
Run the script via:
```
bash download_gdrive.sh fileid filename
```
