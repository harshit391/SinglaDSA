```
class Solution {
    public int[] getConcatenation(int[] nums) {
        int N = nums.length;

        int[] newArr = new int[N * 2];

        for (int i = 0; i < N; i++)
        {
            newArr[i] = nums[i];
            newArr[i + N] = nums[i];
        }

        return newArr;
    }
}
```