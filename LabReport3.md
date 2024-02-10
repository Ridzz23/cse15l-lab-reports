# Lab Report 3

# Part One - Bugs

The buggy program : 
```
public class buggyProgram {
    public int negativeCounter(int[] nums) {
        int counter = 0;
        for (int i : nums) {
            if (i <= 0) {
                counter++;
            }
        }
        return counter;
    }
}

```

A failure-inducing input : 

```
    @Test
    public void testFails() {
        int negNums = bp.negativeCounter(listWithZeros);
        assertEquals(2, negNums);
    }
```

A non-failure inducing input:

```
    @Test
    public void testPasses() {
        int negNums = bp.negativeCounter(listWithBoth);
        assertEquals(2, negNums);
    }
```

The Bug :
```
    public int negativeCounter(int[] nums) {
        int counter = 0;
        for (int i : nums) {
            if (i <= 0) {
                counter++;
            }
        }
        return counter;
    }
```


The Fixed code :

```
    public int negativeCounter(int[] nums) {
        int counter = 0;
        for (int i : nums) {
            if (i < 0) {
                counter++;
            }
        }
        return counter;
    }
```
