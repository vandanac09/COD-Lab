# Program 1: 
### Statement: Write an Assembly program for calculating  x = (y + m) - (L - D) + (Z + C) - D, where x, y, m, L, D, Z, C are elements of 32-bits wide. 

lw t0, y         # Load y into t0
   
lw t1, m     # Load m into t1

lw t2, L     # Load L into t2

lw t3, D     # Load D into t3
    
lw t4, Z     # Load Z into t4

lw t5, C     # Load C into t5

add t6, t0, t1   # t6 = y + m

sub t7, t2, t3   # t7 = L - D

sub t6, t6, t7   # t6 = (y + m) - (L - D)

add t8, t4, t5   # t8 = Z + C

add t6, t6, t8   # t6 = (y + m) - (L - D) + (Z + C)

sub t6, t6, t3   # t6 = (y + m) - (L - D) + (Z + C) - D

la t9, x         # Load address of x into t9

sw t6, 0(t9)     # Store the result in memory at x
