---
title: Geometry and Metric Spaces
---

In my senior year of college, I took a course on Euclidean and non-Euclidean Geometry.[^1] Euclidean Geometry was codified by the Greek mathematician Euclid, in his book **Elements**. It's likely what you think of when you think about Geometry. In this blog post I'll look at what happens if we replace a key part of this geometry we're used to. I'll also touch on a generalization that this exploration leads to, and some fun examples. 

# Euclidean Geometry

Euclid defines a few axioms[^2] that serve as the base of his Geometry. We'll focus on one in particular, which has come to be known as the "Parallel Posulate".

> If a line segment intersects two straight lines forming two interior angles on the same side that sum to less than two right angles, then the two lines, if extended indefinitely, meet on that side on which the angles sum to less than two right angles.

The wording can be a bit tricky, but modern mathematicians have come up with different, equivalent[^3] phrasings. I like **Playfair's axiom**, which reads

> In a plane, given a line and a point not on it, at most[^4] one line parallel to the given line can be drawn through the point.

This is a lot simpler, and we can visualize it pretty easily. 

{{< tabs tabTotal="2" tabID="1" tabName1="Image" tabName2="Sage" >}}
{{< tab tabNum="1" >}}

![Visualization of parallel lines and a point](/images/spaces/playfair.png)

{{< /tab >}}
{{< tab tabNum="2" type="raw">}}

<div class="sage">
  <script type="text/x-sage">
x = line([(0, 0), (5, 5)])
x += line([(0, 1), (5, 6)], rgbcolor=(1, 0, 0))
x += point([(1, 2)], rgbcolor=(0, 1, 0))
x 
  </script>
</div>

{{< /tab >}}
{{< /tabs >}}

What happens if we throw away this postulate and replace it with something else?

## Elliptical Geometry

Suppose we said that **zero** parallel lines exist[^5], or to match Playfair's langugage,

> In a plane, given a line _l_ and a point _p_ not on it, all lines through _p_ intersect _l_

What would such a space look like? I'd encourage pondering this for awhile, and sketching some examples. 

Luckily, we already know a great example of such a space. Consider the surface of a sphere, and the following definition as a "line" on this surface:

> A **Great Circle** is the largest circle that can be drawn on a given sphere.

Probably the best known example of a great circle is the Earth's equator. 

{{< tabs tabTotal="2" tabID="2" tabName1="Image" tabName2="Sage" >}}
{{< tab tabNum="1" >}}

![Visualization of an equator on a sphere](/images/spaces/equator.png)

{{< /tab >}}
{{< tab tabNum="2" type="raw">}}

<div class="sage">
  <script type="text/x-sage">
x = sphere((0,0,0),1,color='red')
x += circle((0, 0), 1.01, color='blue', thickness=2)
x
  </script>
</div>

{{< /tab >}}
{{< /tabs >}}


To prove that this space fulfills the stated axiom, we need to simply pick a point _p_ on this sphere, and prove that any great circle through it must cross through the great circle we picked - in this case, our equator. Intuitively, you might see that if you want to do a full rotation around, you'll have to cross the equator to get the needed length for the great spehere.

So now we have a space where parallel lines don't exist, and it's pretty easy to visualize. 

Consider the triangle, and real world examples in plane paths.

When we put map stuff onto it, it bulges out, so pos curv

## Hyperbolic Geometry

How about the case where we have more than one parallel line? Admittedly, this is trickier

hyperboloid, neg curvature 

# Generalizing Geometry

We've taken a look at how changing the axioms can change the properties of the space we're dealing with. My next questions were along the lines of "Is there a generalization? How do these examples fit into that generalization? What other interesting examples are there?"[^6]. Let's answer these!

## "Is there a generalization?"

Yes! 

A **Metric Space** is an object with two parts. First, a set $M$. Usually, this will be a set of vectors, but it could also comprised of functions or even strings.

Second, we need a _metric_ $d(a, b): M \times M \rightarrow \mathcal{R}$, or a "distance" that we can use to compare items from these sets. This metric has to follow a few axioms:

1. $d(x, y) = 0 \iff x = y$
2. $d(x, y) = d(y, x)$
3. $d(x, z) \leq d(x, y) + d(y, z)$

In plain English, that is

1. A point has distance 0 from itself.
2. Two points have the same distance from each other.
3. A direct path will always have the shortest distance. This expression is also known as the Triangle Inequality.

These are all reasonable requirements for a distance function, and it's not too hard to show that normal Euclidean distance ($d_e (a, b) = \sqrt{(a_x - b_x)^2 + (a_y - b_y)^2}$ in the 2d plane) follows all these rules. Try it!

From these axioms, we can derive that $d(x, y) \geq 0$ in just a few steps. I also recommend that you try showing this!

## "How do these examples fit into that generalization?"

The metrics for elliptic and hyperbolic geometry were more complicated that I'd have liked them to be. Either way, let's take a look by thinking about what a distance _should_ look like for these spaces, and how their metrics stack up. I won't be deriving them, but will provide links to derivations I found good.

### Elliptic Metric

What is "distance" on a sphere? WORDS but it's going along the surface. Look at arc, calculate it out, bingo bango done.

$$d_S(p,q)=~\text{min}\left\{2\arctan\left(\left|\frac{q - p}{1+\overline{p}q}\right|\right), 2\arctan\left(\left|\frac{1+\overline{p}q}{q-p}\right|\right)\right\}$$

What?

### Hyperbolic Metric

What does distance look like in hyperbolic geometry? If we recall our visualization of hyperbolic space, then we 

## "What other interesting examples are there?"

Back to fun stuff!

### Levenshtein Distance

### Taxicab / Manhattan Geometry

### Post Office Geometry

### Chebyshev Geometry

# So what?


# Example Tab / Sage

{{< tabs tabTotal="2" tabID="1" tabName1="Image" tabName2="Sage" >}}
{{< tab tabNum="1" >}}

3

{{< /tab >}}
{{< tab tabNum="2" type="raw">}}

<div class="sage">
  <script type="text/x-sage">1+2</script>
</div>

{{< /tab >}}
{{< /tabs >}}

# References, etc.

# Footnotes
[^1]: We followed "The Four Pillars of Geometry" by John Stillwell.
[^2]: Euclid defines 5 axioms, though by modern standards they're imprecise and incomplete. Still, they're good enough for our uses. See https://en.wikipedia.org/wiki/Euclidean_geometry#Axioms.
[^3]: Equivalent only when taken together with Euclid's other axioms (which together form "Neutral Geometry"). 
[^4]: In Euclidean Geometry, this turns out to be "exactly one", since from the other axioms we can prove that a parallel line exists.
[^5]: If we say this, we actually have to make some changes to the other axioms to have consistent definitions. See 
[^6]: In an earlier version of this post, I didn't include any details about changing the parallel postulate. This was very unsatisfying.