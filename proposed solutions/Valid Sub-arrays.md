# Valid Sub-arrays Problem Solution

## Approach- Pure Bruteforce
```
arr=[3,2,1]
counter=len(arr) 
for i in range(2,len(arr)+1):
	for j in range (len(arr)-i+1):
		flag=1
		for k in range (i):
			if arr[j]>arr[k+j]:
				flag=0
				break
		if flag :
			counter+=1

print (counter)

```