class Solution {
    public int maximumGood(int[][] sts) {
        // 1. generate bitmask
        int n = sts.length;
        int res = 0;
        
        for (int i = (int) Math.pow(2, n); i < (int) Math.pow(2, n + 1); i++) {
            String bitmask = Integer.toBinaryString(i).substring(1);
            boolean conflict = false;
            for (int j = 0; !conflict&&j < n; j++) {
                if (bitmask.charAt(j) == '1') {
                    // 2. check his statements to others so we know if there's a conflict. 
                    for(int k = 0; !conflict&&k< sts[j].length; k++) {
                        if (sts[j][k]!=2 && sts[j][k] != bitmask.charAt(k)-'0') {
                            // this indicates there's a conflict, so this guy is not good as we assumed
                            conflict=true;
                        }
                    }
                }
            }
            if(!conflict) {
                int temp = 0;
                for(int x = 0; x< bitmask.length(); x++){
                    temp+=bitmask.charAt(x)-'0';
                }
                res = Math.max(temp, res);
            }
        }
        return res;
    }
}