```
class Solution {
    public boolean wordPattern(String pattern, String s) {
        
        String[] map = new String[26];
        Set<String> used = new HashSet<>();

        int N1 = pattern.length();

        String[] words = s.split(" ");

        int N2 = words.length;

        if (N1 != N2) return false;

        if (N1 == 0) return true;

        map[pattern.charAt(0) - 'a'] = words[0];
        used.add(words[0]);

        for (int i = 1; i < N1; i++)
        {
            if (map[pattern.charAt(i) - 'a'] != null)
            {
                if (map[pattern.charAt(i) - 'a'].compareTo(words[i]) != 0)
                {
                    return false;
                }
            }
            else
            {
                if (used.add(words[i]))
                {
                    map[pattern.charAt(i) - 'a'] =  words[i];
                }

                else return false;
            }
        }

        return true;
    }
}
```