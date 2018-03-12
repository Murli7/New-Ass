# New-Ass
//Question 1-
//Implement pow(x, n) % d.
//n other words, given x, n and d,
//find (xn % d)
int Solution::pow(int x, int n, int d) {
    // Do not write main() function.
    // Do not read input, instead use the arguments to the function.
    // Do not print the output, instead return values as specified



	if (n == 0) return 1 % d;

    long long ans = 1, base = x;
    
	while (n > 0) {
        // We need (base ** n) % p. 
        // Now there are 2 cases. 
        // 1) n is even. Then we can make base = base^2 and n = n / 2.
        // 2) n is odd. So we need base * base^(n-1) 
        if (n % 2 == 1) {
            ans = (ans * base) % d;
            n--;
        } 
		else {
            base = (base * base) % d;
            n /= 2;
        }
    }
    
    if (ans < 0) ans = (ans + d) % d;
    return ans;    
}
