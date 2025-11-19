# TIL: Bash Parameter Expansion (%, %%, #, ##)

## Suffix Removal (from the right)

- `${var%pattern}` → remove **shortest** suffix matching pattern  
- `${var%%pattern}` → remove **longest** suffix matching pattern

**Example**
```bash
var="abc.def.ghi"
echo ${var%.*}   # → abc.def
echo ${var%%.*}  # → abc
```

## Prefix Removal (from the left)

- `${var#pattern}` → remove shortest prefix matching pattern
- `${var##pattern}` → remove longest prefix matching pattern

Example
```bash
path="/home/user/docs/file.txt"
echo ${path#*/}   # → home/user/docs/file.txt
echo ${path##*/}  # → file.txt
```

## Summary:
|Syntax|Side|Match|Removes|
|------|----|----|--------|
|${var%pattern}|Right|Shortest|Last minimal suffix|
|${var%%pattern}|Right|Longest|Largest suffix|
|${var#pattern}|Left|Shortest|First minimal prefix|
|${var##pattern}|Left|Longest|Largest prefix|
