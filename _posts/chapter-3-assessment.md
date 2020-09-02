set any global chunk options using knitr::opts\_chunk$set(…)
============================================================

\`\`\`

Introduction
------------

We will be looking at the `ChickWeight` dataset from the *datasets*
package.

The `ChickWeight` dataset contains 578 observations of 4 variables.

You can read more about `ChickWeight` by typing `?ChickWeight` in the
console when *datasets* is loaded.

Let’s have a look at the first few lines of `ChickWeight`.

{% highlight r %} head(ChickWeight) {% endhighlight %}

{% highlight text %} \#\# weight Time Chick Diet \#\# 1 42 0 1 1 \#\# 2
51 2 1 1 \#\# 3 59 4 1 1 \#\# 4 64 6 1 1 \#\# 5 76 8 1 1 \#\# 6 93 10 1
1 {% endhighlight %}

The description of `ChickWeight` is as follows:

> Weight versus age of chicks on different diets

Lets plot some aspects of `ChickWeight` to have a look.

Discussion
----------

First we’ll plot `Time` *versus* `weight` for the entire dataset.

{% highlight r %} plot &lt;- ggplot(ChickWeight, aes(x=Time, y=weight))
+ geom\_point() {% endhighlight %}

We’d expect `weight` to go up over time. Let’s add a smoothed mean to
the graph using `geom_smooth()`.

{% highlight r %} plot + geom\_smooth() {% endhighlight %}

{% highlight text %} \#\# `geom_smooth()` using method = ‘loess’ and
formula ‘y ~ x’ {% endhighlight %}

![](../images/time-versus-weigh-with-mean-1.png)

Hmm, perhaps the `Diet` might affect `weight` gain. Let’s differentiate
our data points by changing the colour according to `Diet`.

{% highlight r %} plot + aes(color=Diet) {% endhighlight %}

![](../images/time-versus-weigh-with-mean-by-diet-1.png)

That’s a bit hard to read. Facet the graphs by `Diet` as well so that
each different value of `Diet` has its own plot.

{% highlight r %} plot + aes(color=Diet) + facet\_grid(.~Diet) {%
endhighlight %}

![](../images/time-versus-weigh-with-mean-facetted-by-diet-1.png)

Add a layer to the graph which indicates mean ± standard error for each
diet. Draw these in black so they can be more easily seen.

{% highlight r %} plot + aes(color=Diet) +
facet\_grid(.~Diet)+stat\_summary(color=“black”,alpha=3/4,size=.4) {%
endhighlight %}

{% highlight text %} \#\# No summary function supplied, defaulting to
`mean_se()` \#\# No summary function supplied, defaulting to `mean_se()`
\#\# No summary function supplied, defaulting to `mean_se()` \#\# No
summary function supplied, defaulting to `mean_se()` {% endhighlight %}

![](../images/time-versus-weigh-with-mean-facetted-by-diet-with-mean-and-se-1.png)

Let’s tidy this up a bit by adding units to the axis labels. Add `(g)`
to the y-axis label and `(days)` to the x-axis label.

{% highlight r %} plot + aes(color=Diet) + facet\_grid(.~Diet)+
stat\_summary(color=“black”,alpha=3/4,size=.4)+labs(x = “(days)”, y =
“(g)”) {% endhighlight %}

{% highlight text %} \#\# No summary function supplied, defaulting to
`mean_se()` \#\# No summary function supplied, defaulting to `mean_se()`
\#\# No summary function supplied, defaulting to `mean_se()` \#\# No
summary function supplied, defaulting to `mean_se()` {% endhighlight %}

![](../images/time-versus-weigh-with-mean-facetted-by-diet-labelled-1.png)

Finally, add a title to the plot: `Chick weight over time by diet`.

{% highlight r %} plot + aes(color=Diet) + facet\_grid(.~Diet)+
stat\_summary(color=“black”,alpha=3/4,size=.4)+labs(x = “(days)”, y =
“(g)”,title=“Chick weight over time by diet”) {% endhighlight %}

{% highlight text %} \#\# No summary function supplied, defaulting to
`mean_se()` \#\# No summary function supplied, defaulting to `mean_se()`
\#\# No summary function supplied, defaulting to `mean_se()` \#\# No
summary function supplied, defaulting to `mean_se()` {% endhighlight %}

![](../images/time-versus-weigh-with-mean-facetted-by-diet-labelled-with-title-1.png)

Out of curiosity, let’s try facetting by `Chick` instead (but leaving
the colour set by `Diet`):

{% highlight r %} plot+aes(color=Diet) + facet\_grid(.~Chick) {%
endhighlight %}

![](../images/time-versus-weigh-with-mean-facetted-by-chick-labelled-1.png)
This graph is very hard to read!

Questions
---------

1.  From the graphs, which diet seems to result in improved weight gain?

Since all chicks will gain weight over time, I am looking for which diet
led to an increased weight gain compared to the other diets. From the
graphs, I observe that Diet 3 resulted in the most significant weight
gain. At Day 20, Diet 3 had the largest mean weight, and it’s standard
error lower bound value was more than the other three diet’s standard
error upper band value.

1.  From the graphs, which chick(s) may have died during the course of
    the experiment?

From the Diet 2 graph, I observe a chick’s weight that plateaus at about
50 grams on Day 7 and ceases to grow for the remainder of the days. I
would imagine this chick may have died during the course of the
experiment due to no growth in size.
