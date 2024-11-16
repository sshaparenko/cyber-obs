A “canonical name“ (CNAME) records points from an alias domain to a “canonical domain“.

For example, suppose `blog.example.com` has a CNAME records with a value of `exaple.com`. 

This means, when a DNS hits the DNS records for `blog.example.com`, it actually triggers another DNS lookup to `example.com`, returning it’s IP address via its [[A record]].

In this case we would say, that `example.com` is a CNAME of `blog.example.com`