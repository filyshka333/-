#include <iostream> 
#include <math.h> 
using namespace std; 
class Numb{ 
private: 
 int n,a[10]; 
public: 
 void print(){ 
 for(int i=0; i<n;i++) 
 { 
 cout<<a[i]<<" "; 
 } 
  cout<<"\n"; 
} 
 void input(){ 
  for (int i=0;i<n;i++) 
  { 
   cout<<"a["<<i<<"]="; 
   cin>>this->a[i]; 
  } 
 } 
 void merge(int list[],int start,int end,int mid){ 
 int mergedList[10]; 
 int i = start; 
 int j = mid + 1; 
 int k = start; 
  while (i <= mid && j <= end) { 
   if (list[i] < list[j]) { 
    mergedList[k++] = list[i++]; 
   } else { 
    mergedList[k++] = list[j++]; 
   } 
  } 
   
  while (i <= mid) { 
   mergedList[k++] = list[i++]; 
  } 
   
  while (j <= end) { 
   mergedList[k++] = list[j++]; 
  } 
   
  for (i = start; i <= end; ++i) { 
   list[i] = mergedList[i]; 
  } 
 } 
  
 void merge_sort(int list[], int start, int end){ 
  if (start < end){ 
   mid =(start + end) /2; 
   merge_sort(list, start,mid); 
   merge_sort(list,mid+1,end); 
   merge(list, start, end,mid); 
  } 
 } 
public: 
 
 void merg(int list[],int start, int end, int mid){ 
  int mergList[10]; 
  int i, j, k; 
  i = start; 
  k = start; 
  j = mid + 1; 
   while(i <= mid && j <= end){ 
    if(list[i] < list[j]){ 
     mergList[k] = list[i]; 
     k++; 
     i++; 
    } 
    else{ 
     mergList[k] = list[j]; 
     k++; 
     j++; 
    } 
   } 
  while(i <= mid){ 
   mergList[k] = list[i]; 
   k++; 
   i++; 
  } 
  while (j <= end){ 
   mergList[k] = list[j]; 
   k++; 
   j++; 
  } 
  for (i = start; i<k; i++){ 
   list[i] = mergList[i]; 
  } 
 } 
 
}; 
int main () 
{ 
Numb num; 
 num.n = 10; 
 num.input(); 
 num.merge_sort(num.a, num.n - 1); 
  
 num.print(); 
  
  
  
  
 return 0; 
}
