def bperm(d): #returns the permutation bperm d for any Dyck path d
    n = d.semilength()
    c = [0] * (2*n)
    Uindices = []
    Dindices = []
    for i in range(2*n):
        if d[i] == 1:
            Uindices.append(i)
        else:
            Dindices.append(i)
    T = [[Uindices[i], Dindices[i]] for i in range(n)]
    for i in T[0]:
        c[i] = n
    for i in range(2*n):
        if c[i] == 0:
            k = c[i - 1]
            for m in range(n):
                if i in T[m]:
                    break
            if k - 1 not in c:
                for j in T[m]:
                    c[j] = k - 1
            if k - 1 in c:
                for j in range(2*n):
                    if c[j] > 0 and c[j] < k:
                        c[j] -= 1
                for j in T[m]:
                    c[j] = k - 1
    return Permutation([c[i] for i in Uindices])
