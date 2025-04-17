#include <iostream>
#include <vector>
#include <climits>

using namespace std;

int minCoinsBruteForce(vector<int>& coins, int k) {
    if (k == 0) return 0;
    if (k < 0) return INT_MAX;

    int result = INT_MAX;
    for (int coin : coins) {
        int subResult = minCoinsBruteForce(coins, k - coin);
        if (subResult != INT_MAX)
            result = min(result, subResult + 1);
    }

    return result;
}

int main() {
    vector<int> coins = {2, 4, 5};
    int k = 10;
    int result = minCoinsBruteForce(coins, k);
    
    if (result == INT_MAX)
        cout << "Not possible to form the amount" << endl;
    else
        cout << "Minimum coins needed (Brute-force): " << result << endl;
    
    return 0;
}
