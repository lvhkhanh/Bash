# Bash
## Subprocess reset variable
```
$arr = "find ./ type -f"
# Should avoid
$arr | while read item;
do
  # $i reset to 0
  $i = `expr $i + 1`
  echo $i
done

# Recommended
for item in $arr;
do
  $i = `expr $i + 1`
  echo $i
done

while read item;
do
  $i = `expr $i + 1`
  echo $i
done < <($arr)
```
