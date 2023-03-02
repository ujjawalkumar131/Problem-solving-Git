Bruteforce Logic :-

1. Sort and return arr[n-2] This will not work for duplicates in array. TC(nlogn)

2. To work sort and return we have to make sure second largest is not the largest

code :-

```cpp
int print2largest(int arr[], int n) {

	    if(n<2)
	    return -1;
	    int lar = INT_MIN;
	    int slar = INT_MIN;

	    sort(arr,arr+n);

	    for(int i = 0 ; i <n;i++)
	     {
	         lar = max(lar,arr[i]);

	     }


	     for(int i = n-2; i>=0;i--)
	     {
	         if(arr[i] !=lar)
	         {
	             slar = arr[i];
	             break;

	         }
	     }

	     if(slar<0) slar = -1;

	    return slar;


	}
    TC- o(NLOGN)
```

Better Logic :-

1. In first pass find out the largest.
2. In second pass find out secondlargest but make sure that seclargest is not equal to largest.  
   code :-

```cpp
int print2largest(int arr[], int n) {

	    if(n<2)
	    return -1;
	    int lar = INT_MIN;
	    int slar = INT_MIN;

	    for(int i = 0 ; i <n;i++)
	     {
	         lar = max(lar,arr[i]);

	     }

	     for(int i = 0; i<n;i++)
	     {
	         if(arr[i] > slar && arr[i] !=lar)
	         {
	             slar = arr[i];

	         }
	     }

	     if(slar<0) slar = -1;

	    return slar;


	}
};
Tc- O(2N)
```
Optimal approach :-   
Get solution in single pass only   

1)Logic is that take the largest element as first element and the smallaest one is -1 at initially.   
2) travese entire array only once and get out second largest by if else conditions bcz if any new largest found then old largest become seclargest and new arr[i] become largest.  


code :-  
```cpp
int lar = arr[0];
	    int slar = -1;
	    
	    
	    for(int i = 1 ; i <n ;i++)
	    {
	        
	        if(arr[i]>lar)
	        {
	                slar = lar;
	                lar = arr[i];
	            }
	            else if ( arr[i] < lar && arr[i]>slar)
	            {
	                slar = arr[i];
	            }
	            
	            
	        }
	       
             return slar;


             TC - O(N) single pass solution.
	    ```
