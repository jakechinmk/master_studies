
<!-- rnb-text-begin -->

---
title: "lecture_07"
output: html_notebook
---
 
Algorithm Slide 6

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQTwtIG1hdHJpeChkYXRhPWMoMiwwLDEsMCwxLDAsMSwwLDIpLCBucm93PTMsIG5jb2w9Mylcbms8LSAxXG5yIDwtIDBcbnAgPC0gbnJvdyhBKVxuZXBzIDwtIDEuMGUtMTBcblxud2hpbGUgKGsgPD0gcCl7XG4gIGQgPC0gQVtrLCBrXVxuICBpZiAoYWJzKGQpIDwgZXBzKVxuICB7XG4gICAgQVtrLCBdIDwtIDBcbiAgICBBWywga10gPC0gMFxuICB9XG4gIGVsc2VcbiAge1xuICAgIEFbaywgXSA8LSBBW2ssIF0gLyBkXG4gICAgcHJpbnQoQVtrLCBdKVxuICAgIHIgPC0gciArIDFcbiAgICBmb3IgKGkgaW4gMTpwKVxuICAgIHtcbiAgICAgIGlmIChpIT1rKVxuICAgICAge1xuICAgICAgICBjMSA8LSBBW2ksIGtdXG4gICAgICAgIEFbaSwgXSA8LSBBW2ksIF0gLSBjMSpBW2ssIF1cbiAgICAgICAgQVtpLCBrXSA8LSAtYzEvZFxuICAgICAgICBBW2ssIGtdIDwtIDEvZFxuICAgICAgICBcbiAgICAgIH1cbiAgICB9XG4gIH1cbiAgayA8LSBrICsgMVxufVxuYGBgIn0= -->

```r
A<- matrix(data=c(2,0,1,0,1,0,1,0,2), nrow=3, ncol=3)
k<- 1
r <- 0
p <- nrow(A)
eps <- 1.0e-10

while (k <= p){
  d <- A[k, k]
  if (abs(d) < eps)
  {
    A[k, ] <- 0
    A[, k] <- 0
  }
  else
  {
    A[k, ] <- A[k, ] / d
    print(A[k, ])
    r <- r + 1
    for (i in 1:p)
    {
      if (i!=k)
      {
        c1 <- A[i, k]
        A[i, ] <- A[i, ] - c1*A[k, ]
        A[i, k] <- -c1/d
        A[k, k] <- 1/d
        
      }
    }
  }
  k <- k + 1
}
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiWzFdIDEuMCAwLjAgMC41XG5bMV0gMCAxIDBcblsxXSAtMC4zMyAgMC4wMCAgMS4wMFxuIn0= -->

```
[1] 1.0 0.0 0.5
[1] 0 1 0
[1] -0.33  0.00  1.00
```



<!-- rnb-output-end -->

<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuQVxuYGBgIn0= -->

```r
A
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiICAgICAgWywxXSBbLDJdICBbLDNdXG5bMSxdICAwLjY3ICAgIDAgLTAuMzNcblsyLF0gIDAuMDAgICAgMSAgMC4wMFxuWzMsXSAtMC4zMyAgICAwICAwLjY3XG4ifQ== -->

```
      [,1] [,2]  [,3]
[1,]  0.67    0 -0.33
[2,]  0.00    1  0.00
[3,] -0.33    0  0.67
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->

