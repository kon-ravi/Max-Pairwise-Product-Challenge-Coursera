# Max-Pairwise-Product-Challenge-Coursera
This is the code which passes all the test case of the problem . Stress testing helps a lot.

#include <iostream>
#include <vector>
using namespace std ;

long long MaxPairwiseProduct(const vector<int>& numbers) {
    int n = numbers.size();

    int max_index1 = -1;
    for (int i = 0; i < n; ++i)
        if ((max_index1 == -1) || (numbers[i] > numbers[max_index1]))
            max_index1 = i;

    int max_index2 = -1;
    for (int j = 0; j < n; ++j)
        if ((j != max_index1) && ((max_index2 == -1) || (numbers[j] > numbers[max_index2])))
            max_index2 = j;

    return ((long long)(numbers[max_index1])) * numbers[max_index2];
}

int main() {
    int n;
    cin >> n;
    vector<int> numbers(n);
    for (int i = 0; i < n; ++i) {
        cin >> numbers[i];
    }
    long long product = MaxPairwiseProduct(numbers);
    cout << product << "\n";
    return 0;
}
