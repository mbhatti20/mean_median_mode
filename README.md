# mean_median_mode
find the mean,median and mode of the unordered list or array
        
        
        
       #include<iostream>
      #include<algorithm>
      #include<cmath>
      using namespace std;
      void mod(int array[],int n)
      {  std::sort(array,array+n);
      int number = array[0];
      int mode = number;
      int count = 1;
      int countMode = 1;

      for (int i=1; i<n; i++)
      {
            if (array[i] == number) 
            { // count occurrences of the current number
               ++count;
            }
            else
            { // now this is a different number
                  if (count > countMode) 
                  {
                        countMode = count; // mode is the biggest ocurrences
                        mode = number;
                  }
                 count = 1; // reset count for the new number
                 number = array[i];
        }
      }

      cout<< mode << endl;
      }
      double median(int A[],int n)
      {	std::sort(A,A+n);
          double med;
        if(n%2==0)
        {
          return med=((A[n/2-1]+A[n/2])/2.0);
        }
         if(n%2!=0)
        {
          return med=ceil(A[n/2]);
        }
       return 0;
      }
      double mean(int A[],int n)
      {   double sum=0;
          for(int i=0;i<n;i++)
          {
              sum= sum+A[i];
          }
       return sum/n;
      }
      int main()
      {   
       int n;
          cin>>n;
          int A[n];
          for(int i=0;i<n;i++)
          {
              cin>>A[i];
          }
          cout<<mean(A,n)<<'\n'<<median(A,n)<<'\n';
          mod(A,n);
      }
