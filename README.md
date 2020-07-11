# Code
n=int(input())
s=input()
r=set()
c=0
v=set()
while(s!="-1"):   
    s1=s.split(" ")
    if s1[0]=='Q' and len(r)==0:
        c=0
        print(c)
    else:        
        n1=int(s1[1])
        n2=int(s1[2])
        if(s1[0]=='C' ):
            if(n1 not in r and n2 not in r and n1 not in v and n2 not in v):
                r.clear()
                v.clear()
                r.add(n1)
                r.add(n2)
                v.add(n1)
                v.add(n2)               
            else:                
                r.add(n1)
                r.add(n2)
                for i in v:
                    r.remove(i)
                v.clear()
                for i in r:
                    v.add(i)
        if(s1[0]=='Q' and len(r)>0):
            if len(r)%2==0:
                c=c+1
            else:
                c=c-1
            print(c)    
    s=input()  
