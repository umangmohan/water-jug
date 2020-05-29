# water-jug
code for water jug problem
class graph :
    n = -1
    c = 1
    visited = {1 : [0,0]}
    parent = int()
    a = int ()
    b = int ()

def fillA(obb = graph(),p = int()) :
    print("fillA")
    print(p)
    graph.n = graph.n+1
    print(graph.n)
    obj[graph.n] = graph()
    obj[graph.n].a=3
    obj[graph.n].b=obb.b
    obj[graph.n].parent = p
    pp = graph.n
    temp = []
    temp = [obj[graph.n].a , obj[graph.n].b]
    print(temp)
    check = 0
    for i in graph.visited:
        if graph.visited[i] == temp:
            check = 1
    if check == 0:
        graph.c = graph.c+1
        graph.visited[graph.c] = []
        graph.visited[graph.c].append(obj[graph.n].a)
        graph.visited[graph.c].append(obj[graph.n].b)
        fillB(obj[graph.n],pp)
        AtoB(obj[graph.n],pp)
        emptyB(obj[graph.n],pp)
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b
            
def fillB(obb = graph(),p = int()) :
    print("fillB")
    print(p)
    graph.n = graph.n+1
    print(graph.n)
    obj[graph.n] = graph()
    obj[graph.n].a=obb.a
    obj[graph.n].b=4
    obj[graph.n].parent = p
    pp = graph.n
    temp = []
    temp = [obj[graph.n].a , obj[graph.n].b]
    print(temp)
    check = 0
    for i in graph.visited:
        if graph.visited[i] == temp:
            check = 1
    if check == 0:
        graph.c = graph.c+1
        graph.visited[graph.c] = []
        graph.visited[graph.c].append(obj[graph.n].a)
        graph.visited[graph.c].append(obj[graph.n].b)
        fillA(obj[graph.n],pp)
        BtoA(obj[graph.n],pp)
        emptyA(obj[graph.n],pp)
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b

def emptyA(obb = graph(),p = int()) :
    print("emptyA")
    print(p)
    graph.n = graph.n+1
    print(graph.n)
    obj[graph.n] = graph()
    obj[graph.n].a=0
    obj[graph.n].b=obb.b
    obj[graph.n].parent = p
    pp = graph.n
    temp = []
    temp = [obj[graph.n].a , obj[graph.n].b]
    print(temp)
    check = 0
    for i in graph.visited:
        if graph.visited[i] == temp:
            check = 1
    
    if check == 0:
        graph.c = graph.c +1
        graph.visited[graph.c] = []
        graph.visited[graph.c].append(obj[graph.n].a)
        graph.visited[graph.c].append(obj[graph.n].b)
        fillB(obj[graph.n],pp)
        BtoA(obj[graph.n],pp)
        emptyB(obj[graph.n],pp)
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b

def emptyB(obb = graph(),p = int()) :
    print("emptyB")
    print(p)
    graph.n = graph.n+1
    print(graph.n)
    obj[graph.n] = graph()
    obj[graph.n].a=obb.a
    obj[graph.n].b=0
    obj[graph.n].parent = p
    pp = graph.n
    temp = []
    temp = [obj[graph.n].a , obj[graph.n].b]
    print(temp)
    check = 0
    for i in graph.visited:
        if graph.visited[i] == temp:
            check = 1
    
    if check == 0:
        graph.c = graph.c+1
        graph.visited[graph.c] = []
        graph.visited[graph.c].append(obj[graph.n].a)
        graph.visited[graph.c].append(obj[graph.n].b)
        fillA(obj[graph.n],pp)
        AtoB(obj[graph.n],pp)
        emptyA(obj[graph.n],pp)
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b


def AtoB(obb = graph(),p = int()) :
    print("AtoB")
    print(p)
    graph.n = graph.n+1
    print(graph.n)
    obj[graph.n] = graph()
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b
    empty=4-obb.b
    if obj[graph.n].a<=empty:
        obj[graph.n].b=obj[graph.n].b+obj[graph.n].a
        obj[graph.n].a=0
    else:
        obj[graph.n].a=obj[graph.n].a-empty
        obj[graph.n].b=4
    
    obj[graph.n].parent = p
    pp= graph.n
    temp = []
    temp = [obj[graph.n].a , obj[graph.n].b]
    print(temp)
    check = 0
    for i in graph.visited:
        if graph.visited[i] == temp:
            check = 1
    if check == 0:
        graph.c = graph.c+1
        graph.visited[graph.c] = []
        graph.visited[graph.c].append(obj[graph.n].a)
        graph.visited[graph.c].append(obj[graph.n].b)
        fillA(obj[graph.n],pp)
        BtoA(obj[graph.n],pp)
        emptyB(obj[graph.n],pp)
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b

def BtoA(obb = graph(),p = int()) :
    print("BtoA")
    print(p)
    graph.n = graph.n+1
    print(graph.n)
    obj[graph.n] = graph()
    obj[graph.n].parent = p
    pp = graph.n
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b
    empty=3-obb.a
    print(empty)
    if obj[graph.n].b<=empty:
        obj[graph.n].a=obj[graph.n].a+obj[graph.n].b
        obj[graph.n].b=0
    else:
        obj[graph.n].b=obj[graph.n].b-empty
        obj[graph.n].a=3
    temp = []
    temp = [obj[graph.n].a , obj[graph.n].b]
    check = 0
    for i in graph.visited:
        if graph.visited[i] == temp:
            check = 1
    if check == 0:
        graph.c = graph.c+1
        graph.visited[graph.c] = []
        graph.visited[graph.c].append(obj[graph.n].a)
        graph.visited[graph.c].append(obj[graph.n].b)
        emptyA(obj[graph.n],pp)
        fillB(obj[graph.n],pp)
        AtoB(obj[graph.n],pp)
    obj[graph.n].a=obb.a
    obj[graph.n].b=obb.b

obj = {}
graph.n = graph.n+1
obj[graph.n] = graph()
obj[graph.n].parent=-1
obj[graph.n].a=0
obj[graph.n].b=0
fillA(obj[graph.n])
fillB(obj[graph.n])
print(graph.visited)
final =int()
for i in range(graph.n):
    if obj[i].a==0 and obj[i].b==2:
        final = i
        break
graph.n=final

while obj[graph.n].parent > -1 :
    print(obj[graph.n].a,obj[graph.n].b)
    graph.n=obj[graph.n].parent
print(obj[graph.n].a,obj[graph.n].b)
