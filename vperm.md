def can(d, p): #returns can(d, p) where d in a Dyck path of semilength n and p is a permutation of size n
    n = len(p)
    counter1 = 0
    counter0 = 0
    c = []
    for i in range(2*n):
        if d[i] == 1:
            c.append(p[counter1])
            counter1 += 1
        if d[i] == 0:
            c.append(p[counter0])
            counter0 += 1
    return c

def is_contained(d1, d2): #return True if the Dyck path d1 is contained in the Dyck path d2
    n = d1.semilength()
    if d2.semilength() != n:
        print('size error')
        return False
    d1h = d1.heights()
    d2h = d2.heights()
    for i in range(2*n + 1):
        if d1h[i] > d2h[i]:
            return False
    return True

def vperm(d): #returns the permutation vperm d for any Dyck path d
    b = d.reverse().bounce_path().reverse()
    n = d.semilength()
    p = Permutation([n - i for i in range(n)])
    while b != d:
        c = can(b, p)
        for k in range(2*n):
            if b[k] == 0 and b[k + 1] == 1:
                bnew = list(b)
                bnew[k] = 1
                bnew[k + 1] = 0
                bnew = DyckWord(bnew)
                if is_contained(bnew, d):
                    b = bnew
                    break
        j = c[k]
        i = c[k + 1]
        pnew = list(p)
        for k in range(n):
            if p[k] == i:
                pnew[k] = j
            if p[k] >= i + 1 and p[k] <= j:
                pnew[k] -= 1
        p = Permutation(pnew)
    return p
