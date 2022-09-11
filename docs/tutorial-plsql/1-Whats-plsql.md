---
sidebar_position: 1
---
# PL/SQL Intro


PL/SQL stands for **“Procedural Language extensions to the Structured Query Language”**.

## BLOCKS
```SQL title="Blocks"
DECLARE (Optional)

BEGIN (Mandatory)

EXCEPTION (Optional)

END; (Mandatory)
```

**Three Types Of Blocks**
- Anonymous blocks
- Precedure blocks
- Funtion blocks

## OUTPUTS
```SQL title="Output"
BEGIN

DBMS_OUTPUT.PUT_LINE('Hello World');

END;
```

```SQL title="Nested block output"
BEGIN
    dbms_output.put_line('Hello World');
    BEGIN
    dbms_output.put_line('nested_block');
    END;
END;
```