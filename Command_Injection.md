#Command Injection<br/>
- Low security <br/>
    - just tried && whoami
![image](img/CommInj_LOW.png) <br/>
- Medium security <br/>
  - had to look at source code to see how does the code handles operators, saw & and ; is "patched" so I tried different methods (|, ||) 
![image](img/CommInj_MEDIUM.png) <br/>
- High security <br/>
  - have tried same tricks, looked at source again and didn't figure it out, so had to look up guide which pointed me on the "rogue" white space when filtering "|" == "| ", so I used that symbol without space

![img.png](img/CommInj_HIGH.png) <br/>
