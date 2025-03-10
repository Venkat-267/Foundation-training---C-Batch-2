### String Paranthesis Validation:
```
def validation(string):
    stack=[]
    maps={"}":"{","]":"[",")":"("}
    for char in string:
        if char in maps:
            top=stack.pop() if stack else "0"
            if maps[char]!=top:
                return False
        else:
            stack.append(char)
            
    return not stack
    
print(validation("((({{[[([{}]{})]]}}})))"))
```

### Linear Search:

```
def linear_search(array,search):
    for i, element in enumerate(array):
        if element == search:
            return i
    return -1 
array=[1,3,4,5,6]
print(linear_search(array,3))
```

### Binary Search:
```
def binary_search(array,search,l,h):
    if l > h:
        return -1
    mid=(l+h)//2
    if search == array[mid]:
        return mid
    elif search>array[mid]:
        return binary_search(array,search,mid+1,h)
    else:
        return binary_search(array,search,l,mid-1)
    
array=[1,3,4,5,6]
print(binary_search(array,5,0,len(array)-1))
```
