def smallestsubstring(s):
    l=len(s)
    if l<2: return l
    
    dist=set(s)  
    dist_len=len(dist)
    
    k=l+1
 
    a={}
    st=0; itr=1
    a[s[st]]=1
    while itr<l:
 
        if s[itr] in a: a[s[itr]]+=1
 
        else: a[s[itr]]=1
 
        if len(a)==dist_len:
 
            while st<itr and a[s[st]]>1:
                a[s[st]]-=1
                st+=1
            if k>itr+1-st: k=itr+1-st
        itr+=1
 
    print(k)
 
    
s=str(input())
smallestsubstring(s)
