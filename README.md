# INFO 474 - Building a Data Exploration Tool

## Accessible at: http://students.washington.edu/raktos/info474/data-exp-tool/

I made a histogram of the swears contained in several Tarantino movies.

The original version (the author from whom I got the [data](https://github.com/fivethirtyeight/data))
used a stacked bar chart version of my histogram to show both the deaths and the sweatr in each
movie. I don't particularly like stacked bar charts, especially with the generally lower values of deaths
always being at the bottom, because then the comparisons of swears needs to be a comparison of length
instead of one of position. To solve this I attempted to create the visualization as a set of grouped
bar charts throughout the histogram to preserve the use of position. A (mostly broken) prototype of this version can be seen
at thisURL/with-death-bars.html.I did not use this version because the whitespace created by having a slot
for the death bars implied that there was no data for swears for those time sections which is not at all what
I wanted to convey.

To solve this I simply separated them into different graphs entirely. You lose the comparison of deaths to
swears and the ability to see deaths and swears in aggregate, but I do not think those are as useful as making
sure that the data that is there is effectively conveyed without the missing space complication.

We can however still ask many questions about these movies. We get the standard histogram information, we can ask
where in time in the movies the most swears or deaths occur and where they seem to occur most. We cannot directly compare movies because they exist
on separate graphs but we can follow changes. All time sections (each bar) remain the same on each graph, it
simply moves to where and how tall it needs to be. To compare the same time section between different movies we
can just follow the bar as it moves and see what it does. It becomes more difficult when we want to follow more
than one bar at a time as a group but we can aggregate these groups by changing the bin sizes. It should be noted however
that when bin sizes are changed, during the change, bars can no longer be followed to see equivalent times, bins are changing
so the times they represent are not equivalent.

The "movie" control changes the movie we're looking at, it thus changes which movie we're asking questions about.
For example Kill Bill Vol. 1 seems to have most of it's swearing around the beginning. The "type" control allows us
to look at a different data set. For example though most of the swearing is near the beginning of Kill Bill Vol. 1
most of the killing is at the end. Reservoir Dogs, however, though it has most the the killing at the end, there is swearing
all throughout.

Something I was not intending is that you can actually get a sense for how long each movie is in comparison to the
others by examining the width's of the bars when you keep the bin size the same. Django Unchained is much
longer than Reservoir Dogs.