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
