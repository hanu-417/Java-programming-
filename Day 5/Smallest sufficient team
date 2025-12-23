xclass Solution {
    int n, m;
    int target_mask;
    ArrayList<Integer> result = new ArrayList<>();

    Map<String, Integer> memo = new HashMap<>();

    public int[] smallestSufficientTeam(String[] req_skills, List<List<String>> people) {
        int n = req_skills.length;
        int m = people.size();
        target_mask = (1 << n) - 1;

        Map<String, Integer> skillMap = new HashMap<>();

        for (int i = 0; i < n; i++) {
            skillMap.put(req_skills[i], i);
        }

        ArrayList<Integer> people_skills = new ArrayList<>();

        for (List<String> person : people) {
            int skill_bits = 0;
            for (String skill : person) {

                skill_bits |= (1 << skillMap.get(skill));

            }
            people_skills.add(skill_bits);
        }
        ArrayList<Integer> temp = new ArrayList<>();
        solve(people_skills, 0, temp, 0);

        int[] team = new int[result.size()];
        for (int i = 0; i < result.size(); i++) {
            team[i] = result.get(i);
        }

        return team;
    }

    private void solve(ArrayList<Integer> people_skills, int idx, ArrayList<Integer> temp, int mask) {
        if (idx == people_skills.size()) {
            if (mask == target_mask) {
                if (result.size() == 0 || result.size() >= temp.size()) {
                    result = new ArrayList<>(temp);
                }
            }
            return;
        }

        String key = idx  + "_" + mask;
        if(memo.containsKey(key)) {
            if(memo.get(key) <= temp.size()) return;
        }

        memo.put(key, temp.size());

        if (result.size() != 0 && temp.size() >= result.size())
            return; //pruning to make rec. efficient

        //skip
        solve(people_skills, idx + 1, temp, mask);

        // take
        if ( ( mask | people_skills.get(idx) ) != mask) {
            temp.add(idx);
            solve(people_skills, idx + 1, temp, (mask | people_skills.get(idx)));

            temp.remove(temp.size() - 1);
        }
    }
}
