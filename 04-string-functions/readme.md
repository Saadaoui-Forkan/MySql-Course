1. Left | Right | Mid
```
/*
  Left => LEFT(String, Length)
  text => Field Name
*/

SELECT LEFT(text, 3) FROM `try`;

/*
  Mid => MID(String, Position, Length)
  text => Field Name
*/

SELECT MID(text, 2, 3) FROM `try`;

/*
  Right => RIGHT(String, Length)
  text => Field Name
*/

SELECT RIGHT(text, 3) FROM `try`;
```

2. Length | Char_length
```
/*
  Length => LENGTH(String)
  text => Field Name
*/

SELECT LENGTH(text) FROM `try`;

SELECT text, LENGTH(text) FROM `try`; # Select Text Field And Length Although

SELECT text, LENGTH(text) AS count FROM `try`; # Select Length As Count (Alias)

/*
  Char Length => CHAR_LENGTH(String)
  text => Field Name
*/

SELECT text, CHAR_LENGTH(text) AS count FROM `try`; # Select Length As Count (Alias)
```

3. Upper | Lower
```
/*
  Lower Case => LCASE(String)
  text => Field Name
*/

SELECT LOWER(text) FROM `try`;

SELECT LCASE(text) FROM `try`;

/*
  Upper Case => UCASE(String)
  text => Field Name
*/

SELECT UPPER(text) FROM `try`;

SELECT UCASE(text) FROM `try`;

/* Select And Order */

SELECT text, CHAR_LENGTH(text) AS count FROM `try` ORDER BY CHAR_LENGTH(text) ASC;

SELECT text, CHAR_LENGTH(text) AS count FROM `try` ORDER BY CHAR_LENGTH(text) DESC;
```

4. Repeat | Reverse | Replace
```
/*
  Repeat => REPEAT(String, Number Of Repeats)
  text => Field Name
*/

SELECT text, REPEAT(text, 3) AS repeated FROM `try`;

/*
  Replace => REPLACE(String, From, To)
  text => Field Name
*/

SELECT text, REPEAT(text, "a", "@") AS replaced FROM `try`;

SELECT text, REPEAT(text, "http", "https") AS replaced FROM `try`;

UPDATE `try` SET `text` = REPLACE(text, 'http', 'https');

UPDATE `try` SET `text` = REPLACE(text, 'https://', '');

/*
  Reveres => REVERSE(String)
  text => Field Name
*/

SELECT text, REVERSE(text) AS reversed FROM `try`;

UPDATE `try` SET `text` = REVERSE(text);
```

5. Concat | Concat_ws
```
/*
  Concat => CONCAT(String, String, String)
  text => Field Name
*/

SELECT id, text, CONCAT(text, ' Added By Me') AS mytext FROM `try`;

SELECT id, text, CONCAT('First ', text, ' Last') AS mytext FROM `try`;

SELECT
  id, text, CONCAT('This Country Is ', text, ' And Its ID Is ', id)
AS
  mytextwithid
FROM
  `try`;

/*
  Concat => CONCAT_WS(Separator, String, String)
  text => Field Name
*/

SELECT id, text, CONCAT_WS(',', text, ' Added') AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS('-', text, ' Added') AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS('-', text) AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS(',', id, text) AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS(',', id, ' ', text) AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS(',', CONCAT(id, ' '), text) AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS(',', CONCAT(id, ' '), CONCAT(' ', text)) AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS(',', id, REPEAT(text, 2)) AS mytextwithid FROM `try`;

SELECT id, text, CONCAT_WS(',', id, REPEAT(text, 2)) AS mytextwithid FROM `try`;

SELECT id, text, REVERSE(CONCAT(id, text)) AS mytextwithid FROM `try`;

SELECT id, text, REVERSE(CONCAT(id, text, 'Osama')) AS mytextwithid FROM `try`;
```

6. Insert
```
/*
  Insert => INSERT(String, Position, Length, New String)
  text => Field Name
*/

SELECT text, INSERT(text, 3, 2, 'Osama') AS newString FROM `try`;

UPDATE `try` SET text = INSERT(text, 4, 6, 'Serial');

UPDATE `try` SET text = INSERT(text, 6, 4, '#');

UPDATE `try` SET text = INSERT(text, 7, 1, id);
```

7. Trim | Ltrim | Rtrim
```
/*
  Trim => TRIM(Methods[Leading | Trailing | Both] [Remove String] From [String])
  text => Field Name
*/

SELECT text, TRIM(text) AS textWithoutSpace FROM `try`;

SELECT text, TRIM(LEADING FROM text) AS textWithoutSpace FROM `try`;

SELECT text, TRIM(TRAILING FROM text) AS textWithoutSpace FROM `try`;

SELECT text, TRIM(BOTH FROM text) AS textWithoutSpace FROM `try`;

SELECT
  text, TRIM(BOTH FROM text) AS textWithoutSpace,
  CHAR_LENGTH(TRIM(BOTM FROM text)) AS BothTrim
FROM
  `try`;

SELECT
  text, TRIM(BOTH FROM text) AS textWithoutSpace,
  CHAR_LENGTH(TRIM(BOTH FROM text)) AS BothTrim,
CHAR_LENGTH(text) AS textLengthWithoutTrim,
FROM
  `try`;

SELECT
  text, TRIM(LEADING FROM text) AS textWithoutLeadingSpace,
  CHAR_LENGTH(text) AS textLengthWithoutTrim,
  CHAR_LENGTH(TRIM(LEADING FROM text)) AS LeadingTrim,
FROM
  `try`;

SELECT text, TRIM(LEADING '@' FROM text) AS textWithTrim FROM `try`;

SELECT text, TRIM(TRAILING '@' FROM text) AS textWithTrim FROM `try`;

SELECT text, TRIM(BOTH '@' FROM text) AS textWithTrim FROM `try`;

SELECT text, LTRIM(text) AS textWithTrim FROM `try`;

SELECT text, RTRIM(text) AS textWithTrim FROM `try`;
```

8. Lpad | Rpad
```
/*
  LPad => LPAD(String, Length, PaddedString)
  text => Field Name
*/

SELECT text AS MainText, LPAD(text, 3, '') AS TextWithPadded FROM `try`;

SELECT text AS MainText, LPAD(text, 5, '@') AS TextWithPadded FROM `try`;

SELECT text AS MainText, RPAD(text, 5, '@') AS TextWithPadded FROM `try`;
```