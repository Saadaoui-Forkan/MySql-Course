## Data Types
1. Numerics
```
TINYINT           ===> Max Length: 4
SMALLINT          ===> Max Length: 6
MEDIUMINT         ===> Max Length: 9
INT               ===> Max Length: 11
BIGINT            ===> Max Length: 20
```

2. Date And Time
```
Date              ==> YYYY-MM-DD 1000-01-01 To 9999-12-31
Datetime          ==> YYYY-MM-DD HH:Mi:SS
Timestamp         ==> YYYY-MM-DD HH:Mi:SS
Time              ==> HH:Mi:SS
Year              ==> YYYY | YY
```

3. String
```
Char => Character
- Store Fixed Values
- Max Characters 255
- Faster Than VarChar 50%
- Use Static Memory

VarChar => Variable Character
- Store Variable Value
- Max Characters For MySQL 5.0.3+ = 65.535
- Slower Than Char
- Use Dynamic Memory

Text => Store Strings
- Deal & Compared Depend on Encoding
- Store Long Strings

BLOB => Binary Large Object
- Has NO Charset
- Deal & Compared Depend on Numeric Value of The Bytes
- Used To Store Images and Other Files
```