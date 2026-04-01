```
class Solution {
    public boolean wordPattern(String pattern, String s) 
    {   
        int N = pattern.length();

        String[] words = s.split(" ");

        if (words.length != N) return false;

        String[] map = new String[26];
        Set<String> used = new HashSet<>();

        for (int i = 0; i < N; i++)
        {
            int curr = pattern.charAt(i) - 'a';

            if (used.add(words[i]))
            {
                if (map[curr] != null) return false;

                map[curr] = words[i];
            }
            else
            {
                if (map[curr] == null || map[curr].compareTo(words[i]) != 0) return false;
            }
        }

        return true;
    }
}
```