# Gas Station
## https://leetcode.com/problems/gas-station


# Implementation : Brute Force O(N ^ 2)
```java
class Solution {
    public int canCompleteCircuit(int[] gas, int[] cost) {
        for(int i = 0; i < gas.length; i++) {
            int current_stop = i;
            int count = 0;
            int totalGas= gas[i];
            for(; count <= gas.length; count++) {
                int next_stop = current_stop + 1;
                if(next_stop == gas.length)
                    next_stop = 0;
                if(totalGas < cost[current_stop])
                    break;
                else {
                    totalGas = totalGas - cost[current_stop] + gas[next_stop];
                }
                current_stop = next_stop;
            }
            if(count > gas.length)
                return i;
        }
        return -1;
    }
}
```

# References :
https://www.youtube.com/watch?v=wDgKaNrSOEI
