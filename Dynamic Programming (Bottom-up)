#include <iostream>
#include <vector>
#include <climits>

using namespace std;

int minCoinsDP(vector<int>& coins, int k) {
    vector<int> dp(k + 1, INT_MAX);
    dp[0] = 0;

    for (int i = 1; i <= k; ++i) {
        for (int coin : coins) {
            if (i - coin >= 0 && dp[i - coin] != INT_MAX)
                dp[i] = min(dp[i], dp[i - coin] + 1);
        }
    }

    return dp[k] == INT_MAX ? -1 : dp[k];
}

int main() {
    vector<int> coins = {2, 4, 5};
    int k = 10;

    int result = minCoinsDP(coins, k);
    if (result == -1)
        cout << "Not possible to form the amount" << endl;
    else
        cout << "Minimum coins needed (DP): " << result << endl;

    return 0;
}
