class Solution {
    public static List<String> restoreIpAddresses(String s) {
        // Initialize the list to hold all valid IP addresses
        List<String> addresses = new ArrayList<>();
        // Initialize the list to hold the current IP address being built
        List<String> address = new ArrayList<>();
        // Call the recursive helper function to generate all possible IP addresses
        rec(s, 0, address, addresses);
        // Return the list of all valid IP addresses
        return addresses;
    }
    private static void rec(String s, int i, List<String> address, List<String> addresses) {
        // If the current address has 4 segments, check if we have reached the end of the input string
        if (address.size() == 4) {
            if (i == s.length()) {
                // If we have reached the end of the input string, add the current address to the list of valid addresses
                addresses.add(String.join(".", address));
            }
        } else {
            // Try all possible next segments for the current address
            for (int j = i + 1; j <= i + 3 && j <= s.length(); j++) {
                String nextInt = s.substring(i, j);
                // Check if the next segment is valid (between 0 and 255, and not starting with 0 unless it is 0)
                if (Integer.parseInt(nextInt) <= 255 && (nextInt.equals("0") || !nextInt.startsWith("0"))) {
                    // Add the next segment to the current address
                    address.add(nextInt);
                    // Recursively call the function to generate the next segment
                    rec(s, j, address, addresses);
                    // Remove the last segment from the current address
                    address.remove(address.size() - 1);
                }
            }
        }
    }
}

