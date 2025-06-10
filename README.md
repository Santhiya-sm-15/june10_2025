# june10_2025
The problem that I solved today

You are given a string s consisting of lowercase English letters.

Your task is to find the maximum difference diff = a1 - a2 between the frequency of characters a1 and a2 in the string such that:

a1 has an odd frequency in the string.
a2 has an even frequency in the string.
Return this maximum difference.

Code:
class Solution {
    public int maxDifference(String s) {
        int[] freq=new int[26];
        for(char c:s.toCharArray())
            freq[c-'a']++;
        int max=0,min=Integer.MAX_VALUE;
        for(int i=0;i<26;i++)
        {
            if(freq[i]!=0)
            {
                if(freq[i]%2==0)
                    min=Math.min(min,freq[i]);
                else
                    max=Math.max(max,freq[i]);
            }
        }
        return max-min;
    }
}
