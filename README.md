# C++
C++ Problems and Solution

Problem-1:

A child is playing a cloud hopping game. In this game, there are sequentially numbered clouds that can be thunderheads or cumulus clouds. The character must jump from cloud to cloud until it reaches the start again.

There is an array of clouds, c and an energy level e=100 . The character starts from c[0]  and uses  1 unit of energy to make a jump of size k  to cloud c[(i+k)%c.size()]. If it lands on a thundercloud, c[i]=1 , its energy (e) decreases by 2 additional units. The game ends when the character lands back on cloud .

Given the values of n, k, and the configuration of the clouds as an array c, determine the final value of e after the game ends.



💣Solution-1:


               int jumpingOnClouds(vector<int> c, int k) 
                {
                   int level =100;
                   int i = k % c.size();
                   level-= c[i] * 2 + 1; 
                   while(i!=0)
                   {
                   i=(i+k)%c.size();
                   level-=c[i] * 2 + 1;
        
                    }  
                    return level;
      
                 }


Problem-2:

  The distance between two array values is the number of indices between them. Given a, find the minimum distance between any pair of equal elements in the array. If no such value exists, return -1.
  
Example: 

 Input:
                 
                 STDIN           Function
                  -----           --------
                   6               arr[] size n = 6
                   7 1 3 4 1 7     arr = [7, 1, 3, 4, 1, 7]
  
  Output:
  
  
  
                    3
                    
                    
 💣Solution-2:
 
 
 
      int minimumDistances(vector<int> a) {
     int take[a.size()];
     for(int i=0; i<a.size();i++)
          take[i]=-1;
     for(int i=0; i<a.size();i++)
     {
    
      for(int j=0; j<a.size();j++)
      {
         if(i!=j)
         {
             if(a[i] == a[j])
             {
                 int sum  = i-j;
                 int result = abs(sum);
                  take[i] =result;
             }
         }    
      }   
      
         
     }
      int n = sizeof(take) / sizeof(take[0]);
 
    
    sort(take, take + n);
    int result=-1;
    for(int i=0; i<a.size();i++)
    {
        if(take[i]!=-1)
        {
            result=take[i];
            break;
        }
            
    } 
   
     return result;
         
     }










