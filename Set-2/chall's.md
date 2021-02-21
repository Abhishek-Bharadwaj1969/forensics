``` b_challenge       ```
b means binwalk this is the hint use ``` binwalk -e <file_name> ``` and get the flag

``` E _challenge ```
E stands for exiftool and we can use that and find the comment as 696e6374667b337831663730304c5f69735f673030645f215f67756573735f2121217d and coverting this hex to text gives the flag

```FS_challenge ```
it's file forensics use ghex and fix the crc error by inserting the values and get the flag

```s_challenge```
  s -> strings use that convert the "The special sentance: aW5jdGZ7c3RyaW5nc19hcmVfdXNlZnVsfQ==" into ascii as it's base64
``` sh_challenge ```
sh -> steg-hide use strings get the hex and convert the ascii(base-64) into text get the phrase

``` ss_challenge ```
ss -> stegsolve use that and get flag

``` z_challenge ```
z->zbarimg use the tool ``` zbarimg <file_name>  ``` and get flag
