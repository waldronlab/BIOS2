# BIOS2: Biostatistics 621 / 821

R Markdown and .ipynb source code for Levi Waldron's Biostatistics II
lectures and labs is maintained at https://github.com/waldronlab/bios2.

Jupyter Notebooks are also available at
https://notebooks.azure.com/LeviWaldron56/libraries/bios2.

## Conversion of Rmd to ipynb

Here is the shell script I use to convert Rmd files to ipynb. It
relies on [notedown](https://github.com/aaren/notedown), which can be
installed by `pip install notedown`.

```
#!/bin/bash
oldfile=$1
newfile="$(basename "$oldfile" .Rmd).ipynb"
echo Creating "$newfile" from "$oldfile"
notedown $oldfile | grep -v '%%R' > $newfile
```