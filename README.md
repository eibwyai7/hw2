import numpy, sys, time

if (len(sys.argv) != 2):
    print("usage: python %s N" % sys.argv[0])
    quit()

n = int(sys.argv[1])
a = numpy.zeros((n, n)) # Matrix A
b = numpy.zeros((n, n)) # Matrix B
c = numpy.zeros((n, n)) # Matrix C


for i in range(n):
    for j in range(n):
        a[i, j] = i * n + j
        b[i, j] = j * n + i
        c[i, j] = 0

begin = time.time()

res = []
for i in range(0, n):
    row = []
    for j in range(0, n):
        c = 0
        for k in range(0, n):
            c += A[i][k] * B[k][j]
        row.append(c)
    res.append(row)
c = numpy.array(res)


end = time.time()
print("time: %.6f sec" % (end - begin))


total = 0
for i in range(n):
    for j in range(n):
        # print c[i, j]
        total += c[i, j]

print("sum: %.6f" % total) 
