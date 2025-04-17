#include <iostream>
#include <vector>
#include <climits>
#include <unordered_map>

using namespace std;

int minCoinsTopDown(vector<int>& coins, int k, unordered_map<int, int>& memo) {
    if (k == 0) return 0;
    if (k < 0) return INT_MAX;
    if (memo.find(k) != memo.end()) return memo[k];

    int result = INT_MAX;
    for (int coin : coins) {
        int subResult = minCoinsTopDown(coins, k - coin, memo);
        if (subResult != INT_MAX) {
            result = min(result, subResult + 1);
        }
    }

    memo[k] = result;
    return result;
}

int main() {
    vector<int> coins = {2, 4, 5};
    int k = 10;
    unordered_map<int, int> memo;

    int result = minCoinsTopDown(coins, k, memo);

    if (result == INT_MAX)
        cout << "Not possible to form the amount" << endl;
    else
        cout << "Minimum coins needed (Top-down DP): " << result << endl;

    return 0;
}
