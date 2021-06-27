class Solution {
public:
	vector<int> ans;
	vector<pair<int,int>> nums;

	void getRevInv(int i1,int j1,int i2,int j2) {
		int i=i1,c=0;
		vector<pair<int,int>> v;
		while(i1<=j1 && i2<=j2) {
			if(nums[i2].first>=nums[i1].first) v.push_back(nums[i2++]);
			else {
				v.push_back(nums[i1]);
				ans[nums[i1++].second]+= j2-i2+1;
			}
		}
		while(i1<=j1) v.push_back(nums[i1++]);
		while(i2<=j2) v.push_back(nums[i2++]);
		for(auto j: v) nums[i++]=j;
	}

	void merge(int i,int j) {
		if(i==j) return;
		int mid= (i+j)/2;
		if(i!=mid) merge(i,mid);
		if(mid+1!=j) merge(mid+1,j);
		getRevInv(i,mid,mid+1,j);
	}

	vector<int> countSmaller(vector<int>& arr) {
		int n= arr.size();
		ans.clear(); ans.resize(n,0);
		nums.clear();
		for(int i=0;i<n;i++) nums.push_back({arr[i],i});
		merge(0,n-1);
		return ans;
	}
};
