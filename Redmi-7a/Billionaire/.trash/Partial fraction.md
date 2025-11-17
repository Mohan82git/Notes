We have $$\frac{3s+7}{s² -2s-3} = \frac{3s+7}{(s-3)(s+1)}$$
Let 
$$\frac{3s+7}{(s-3)(s+1)}=\frac{A}{(s-3)}+\frac{B}{(s+1)}$$

Multiplying both sides by (s-3) (s+1)

$$3s+7=A(s+1) +B(s-3)$$
Equating coefficients of like powers of S

- S वाले terms = A(s+1)
- बाकी = B(s-3)
2 equations milenge, simultaneous solve Karo ya phir 2 unknowns calc pe dalo

Hence 
$$\frac{3s+7}{(s-3)(s+1)}= \frac{4}{s-3}-\frac{1}{s+1}$$
Now take inverse Laplace of both sides 
$$= L^{-1}\left[{\frac{3s+7}{(s-3)(s+1)}} \right ]$$$$=  L^{-1}\left[{\frac{4}{s-3}} \right ] + L^{-1}\left[{\frac{1}{s+1}} \right ]$$
Done !!

---
For 
$$\frac{1}{(Term 1)(Term 2)(Term 3)}$$
Same procedure till 
Multiply both sides by denominator

You get following type
$$\frac{1}{(S+a)(S+b)(S+c)} $$
$$=\frac{A}{(S+a)}+\frac{B}{(S+b)}+\frac{C}{(S+c)}$$
Equation = A*(बाकी लोगो के denominator) + 
B*(बाकी लोगो के denominator) +
C*(बाकी लोगो के denominator)
$$Equation = A(S+b)(s+c).....$$


FOR A
Substitute A ka denominator I.e (S+a) 
Hence s = -a in 
Equation = A*(baaki logo ke denominator )

For B
Substitute B ka denominator i.e (S+b)
Hence s = -b, in 
Equation = B*(Baaki logo ka denominator )

For C
Substitute C ka denominator i.e (S+c)
Hence s = -c, in 
Equation = C*(Baaki logo ka denominator )

^ ये सब करके जो A, B, C की value मिलेगी उनको नीचे substitute कर दो

$$=\frac{A}{(S+a)}+\frac{B}{(S+b)}+\frac{C}{(S+c)}$$


