# Leetcode-3066

# C++

class Solution {
public:
    int minOperations(vector<int>& nums, int k) {
        priority_queue<long long,vector<long long>,greater<long long>>pq;
        for(int i=0;i<nums.size();i++)
        {
            pq.push(nums[i]);
        }
        int c=0;
        while(1)
        {
            long long a=pq.top();
            if(a>=k)return c;
            pq.pop();
            long long b=pq.top();
            pq.pop();
            long long d=a*2+b;
            //cout<<d<<"\n";
            pq.push(d);
            c++;
        }
        return c;
    }
};

# Python

import heapq

class Solution:
    def minOperations(self, nums, k):
        pq = []
        for num in nums:
            heapq.heappush(pq, num)
        
        c = 0
        while True:
            a = heapq.heappop(pq)
            if a >= k:
                return c
            b = heapq.heappop(pq)
            d = a * 2 + b
            heapq.heappush(pq, d)
            c += 1

# Java

import java.util.PriorityQueue;

class Solution {
    public int minOperations(int[] nums, int k) {
        PriorityQueue<Long> pq = new PriorityQueue<>();
        
        for (int num : nums) {
            pq.add((long) num);
        }
        
        int c = 0;
        while (true) {
            long a = pq.poll();
            if (a >= k) {
                return c;
            }
            long b = pq.poll();
            long d = a * 2 + b;
            pq.add(d);
            c++;
        }
    }
}
