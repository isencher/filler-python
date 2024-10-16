## Documentation

The filler Python library provides a way to sequentially fill a list of data into a docx template, resulting in a batch of pre-filled docx files. For example, a teacher can automatically fill a list of award-winning students into a certificate template, thereby generating a certificate for each student.

## Installation
```
# install from PyPI
pip install filler
```

## Usage
The corresponding values in the list are mapped to the template using **`{{column name}}`**.

```
import filler
import pandas as pd

tpl = 'data/tpl.docx'
data = pd.excel('data/stulist.xlsx')
output_path = 'data/output'
output_name_pat = '{id}-{name}'s-certificate.xlsx'

f = filler.Filler(
    tpl = tpl,
    data = data,
    output_path = output_path,
    output_name_pat = output_name_pat
)

f.fill()
```
After running this script, a batch of certificate docx files for each student will appear in the `data/output` directory.

