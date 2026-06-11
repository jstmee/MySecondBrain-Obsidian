
TARGET DECK: DSA::Standard Template Libraries(STL)::Algorithms

Q: next_permutation(v.begin(),v.end()) and prev_permutation(v.begin(),v.end()) this return null when next permutation not available. and this change in the same vector just like sort.
A: return true or false if next permutation exist or not same for prev
code to print all permutation of number from 1 to n in lexicographic order
```c++
void myf() {
    int n;cin>>n;
    vector<int> v(n);
    for(int i=0;i<n;i++){
        v[i]=i+1;
        cout<<v[i]<<" ";
    }
    cout<<endl;
    while(next_permutation(v.begin(),v.end())){
        for(auto it:v){
            cout<<it<<" ";
        }
        cout<<endl;
    }
}
```
<!--ID: 1780211202805-->


