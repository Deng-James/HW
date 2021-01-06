> **1.NOT**

```
/**
 * Not gate:
 * out = not in
 */

CHIP Not {
    IN in;
    OUT out;

    PARTS:
    // Put your code here:
    Nand(a=in, b=in, out=out);
}
```

```
|  in   |  out  |
|   0   |   1   |
|   1   |   0   |

```

> **2.AND**
```
/**
 * And gate: 
 * out = 1 if (a == 1 and b == 1)
 *       0 otherwise
 */

CHIP And {
    IN a, b;
    OUT out;

    PARTS:
    // Put your code here:
    Nand(a=a,b=b,out=aNandb);
    Nand(a=aNandb,b=aNandb,out=out);
}
```

```
|   a   |   b   |  out  |
|   0   |   0   |   0   |
|   0   |   1   |   0   |
|   1   |   0   |   0   |
|   1   |   1   |   1   |

```
> **3.OR**
```
 /**
 * Or gate:
 * out = 1 if (a == 1 or b == 1)
 *       0 otherwise
 */

CHIP Or {
    IN a, b;
    OUT out;

    PARTS:
    // Put your code here:
    Not(in=a,out=Nota);
    Not(in=b,out=Notb);
    Nand(a=Nota,b=Notb,out=out);
}
```
```
|   a   |   b   |  out  |
|   0   |   0   |   0   |
|   0   |   1   |   1   |
|   1   |   0   |   1   |
|   1   |   1   |   1   |

```

> **4.XOR**
```
/**
 * Exclusive-or gate:
 * out = not (a == b)
 */

CHIP Xor {
    IN a, b;
    OUT out;

    PARTS:
    // Put your code here:
    Not(in=a,out=Nota);
    Not(in=b,out=Notb);
    And(a=Nota,b=b,out=Notab);
    And(a=a,b=Notb,out=aNotb);
    Or(a=Notab,b=aNotb,out=out);
}
```
```
|   a   |   b   |  out  |
|   0   |   0   |   0   |
|   0   |   1   |   1   |
|   1   |   0   |   1   |
|   1   |   1   |   0   |

```

> **5.Mux**
```
/** 
 * Multiplexor:
 * out = a if sel == 0
 *       b otherwise
 */

CHIP Mux {
    IN a, b, sel;
    OUT out;

    PARTS:
    // Put your code here:
    Not(in=sel,out=Notsel);
    And(a=a,b=Notsel,out=aNotsel);
    And(a=sel,b=b,out=selb);
    Or(a=aNotsel,b=selb,out=out);
}
```
```
|   a   |   b   |  sel  |  out  |
|   0   |   0   |   0   |   0   |
|   0   |   0   |   1   |   0   |
|   0   |   1   |   0   |   0   |
|   0   |   1   |   1   |   1   |
|   1   |   0   |   0   |   1   |
|   1   |   0   |   1   |   0   |
|   1   |   1   |   0   |   1   |
|   1   |   1   |   1   |   1   |

```

> **6.DMux**
```
/**
 * Demultiplexor:
 * {a, b} = {in, 0} if sel == 0
 *          {0, in} if sel == 1
 */

CHIP DMux {
    IN in, sel;
    OUT a, b;

    PARTS:
    // Put your code here:
    Not(in=sel,out=Notsel);
    And(a=in,b=Notsel,out=a);
    And(a=in,b=sel,out=b);
}
```
```
|  in   |  sel  |   a   |   b   |
|   0   |   0   |   0   |   0   |
|   0   |   1   |   0   |   0   |
|   1   |   0   |   1   |   0   |
|   1   |   1   |   0   |   1   |

```

![20210106_230215](https://user-images.githubusercontent.com/55796905/103784004-66705b80-5074-11eb-9e34-2a205565ea1c.jpg)
![20210106_230223](https://user-images.githubusercontent.com/55796905/103784010-696b4c00-5074-11eb-9c70-12ec399aa9d1.jpg)
