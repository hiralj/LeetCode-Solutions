// O(n) time, O(n) space
public class Solution {
    public String getHint(String secret, String guess) {
        Map<Character, Integer> charFreq = new HashMap<Character, Integer>();
        List<Integer> indicesForCow = new ArrayList<Integer>();
        char c, d;
        int bull = 0, cow = 0;
        
        populateMap(charFreq, secret);
        for(int i = 0; i < guess.length(); i++) {
            c = guess.charAt(i);
            d = secret.charAt(i);
            if(c == d) {
                bull++;
                charFreq.put(d, charFreq.get(d) - 1);
            } else
                indicesForCow.add(i);
        }
        for(int i : indicesForCow) {
            c = guess.charAt(i);
            if(charFreq.containsKey(c) && charFreq.get(c) > 0) {
                cow++;
                charFreq.put(c, charFreq.get(c) - 1);
            }
        }
        return bull + "A" + cow + "B";
    }
    
    private void populateMap(Map<Character, Integer> charFreq, String secret) {
        char c;
        for(int i = 0; i < secret.length(); i++) {
            c = secret.charAt(i);
            if(charFreq.containsKey(c))
                charFreq.put(c, charFreq.get(c) + 1);
            else
                charFreq.put(c, 1);
        }
    }
}
