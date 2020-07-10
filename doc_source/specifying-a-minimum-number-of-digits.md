# Specifying a minimum number of digits<a name="specifying-a-minimum-number-of-digits"></a>

For format identifiers that return a number, you can specify a minimum number of digits that the format identifier will resolve to\. When you do, the service adds padding zeros before any value that would return fewer digits\.

Use the following syntax to specify the number of digits: **%0\[number of digits\]**\. Put this value just before the final `$` of the format identifier\.

For example, suppose that your video frame height is 720 and you want to specify a minimum of four digits, so that it appears in your file name as `0720`\. To do that, use the following format identifier: **$h%04$**\.

**Note**  
Values that are too large to be expressed in the number of digits you specify resolve with more digits\.