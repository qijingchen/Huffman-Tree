# Huffman-Tree
Implement huffman Tree with a small root heap
#include<iostream>
#include<queue>
#include<functional>
using namespace std;
priority_queue<int, vector<int>, greater<int>>Q;
int main() {
	int n;
	while (scanf_s("%d", &n) != EOF) {
		while (Q.empty() == false)Q.pop();
		int x;
		for (int i = 0; i < n; i++) {
			cin >> x;
			Q.push(x);

		}
		int ans = 0;
		while (Q.size() > 1) {
			int a = Q.top();
			Q.pop();
			int b = Q.top();
			Q.pop();
			ans += a + b;
			Q.push(a + b);
		}
		cout << ans << endl;
	}
	return 0;
}
