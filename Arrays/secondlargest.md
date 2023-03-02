Bruteforce Logic :- \\
1) Sort and return arr[n-2] This will not work for duplicates in array. TC(nlogn) \\
2) To work sort and return we have to make sure second largest is not the largest \\
code :-
``cpp
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
``


