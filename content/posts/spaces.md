---
title: Geometry and Metic Spaces
---

In my senior year of college, I took a course on Euclidean and non-Euclidean Geometry.[^1] Euclidean Geometry was codified by the Greek mathematician Euclid, in his book **Elements**. It's likely what you think of when you think about Geometry. 

Euclid defines a few axioms[^2] that serve as the base of this Geometry. We'll focus on one in particular, which has come to be known as the "Parallel Posulate".

> If a line segment intersects two straight lines forming two interior angles on the same side that sum to less than two right angles, then the two lines, if extended indefinitely, meet on that side on which the angles sum to less than two right angles.

The wording can be a bit tricky, but modern mathematicians have come up with different, equivalent[^3] phrasings. I like **Playfair's axiom**, which reads

> In a plane, given a line and a point not on it, at most[^4] one line parallel to the given line can be drawn through the point.

{{< callout emoji="⚡️" text="TODO: Pic and words" >}}

What happens if we throw away this postulate and replace it with something else?

## Elliptical Geometry

Suppose we said that **zero** parallel lines exist. To remain consistent with the other Axioms, we have to make some changes[^5] to them. That said, what does a space with no parallel lines look like?

## Hyperbolic Geometry

How about the case where we have more than one parallel line?

# Taking an Algebraic View

## Some Examples

# Why we care

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
[^2]: Euclid defines 5 axioms, though by modern standards they're imprecise and incomplete. Still, they're good enough for our uses. 
[^3]: Equivalent only when taken together with Euclid's other axioms (which together form "Neutral Geometry"). 
[^4]: In Euclidean Geometry, this turns out to be "exactly one", since from the other axioms we can prove that a parallel line exists.
[^5]: .